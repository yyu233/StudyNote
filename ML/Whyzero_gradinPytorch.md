In PyTorch, for every mini-batch during the training phase, we typically want to explicitly set the gradients to zero before starting to do backpropragation (i.e., updating the Weights and biases) because PyTorch accumulates the gradients on subsequent backward passes. This accumulating behaviour is convenient while training RNNs or when we want to compute the gradient of the loss summed over multiple mini-batches. So, the default action has been set to accumulate (i.e. sum) the gradients on every loss.backward() call.

Because of this, when you start your training loop, ideally you should zero out the gradients so that you do the parameter update correctly. Otherwise, the gradient would be a combination of the old gradient, which you have already used to update your model parameters, and the newly-computed gradient. It would therefore point in some other direction than the intended direction towards the minimum (or maximum, in case of maximization objectives).

Here is a simple example:

import torch
from torch.autograd import Variable
import torch.optim as optim

def linear_model(x, W, b):
    return torch.matmul(x, W) + b

data, targets = ...

W = Variable(torch.randn(4, 3), requires_grad=True)
b = Variable(torch.randn(3), requires_grad=True)

optimizer = optim.Adam([W, b])

for sample, target in zip(data, targets):
    # clear out the gradients of all Variables 
    # in this optimizer (i.e. W, b)
    optimizer.zero_grad()
    output = linear_model(sample, W, b)
    loss = (output - target) ** 2
    loss.backward()
    optimizer.step()
Alternatively, if you're doing a vanilla gradient descent, then:

W = Variable(torch.randn(4, 3), requires_grad=True)
b = Variable(torch.randn(3), requires_grad=True)

for sample, target in zip(data, targets):
    # clear out the gradients of Variables 
    # (i.e. W, b)
    W.grad.data.zero_()
    b.grad.data.zero_()

    output = linear_model(sample, W, b)
    loss = (output - target) ** 2
    loss.backward()

    W -= learning_rate * W.grad.data
    b -= learning_rate * b.grad.data
Note:

The accumulation (i.e., sum) of gradients happens when .backward() is called on the loss tensor.
As of v1.7.0, Pytorch offers the option to reset the gradients to None optimizer.zero_grad(set_to_none=True) instead of filling them with a tensor of zeroes. The docs claim that this setting reduces memory requirements and slightly improves performance, but might be error-prone if not handled carefully.
