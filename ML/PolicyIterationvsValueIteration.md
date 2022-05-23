
In policy iteration algorithms, you start with a random policy, then find the value function of that policy (policy evaluation step), then find a new (improved) policy based on the previous value function, and so on. In this process, each policy is guaranteed to be a strict improvement over the previous one (unless it is already optimal). Given a policy, its value function can be obtained using the Bellman operator.

In value iteration, you start with a random value function and then find a new (improved) value function in an iterative process, until reaching the optimal value function. Notice that you can derive easily the optimal policy from the optimal value function. This process is based on the optimality Bellman operator.

In some sense, both algorithms share the same working principle, and they can be seen as two cases of the generalized policy iteration. However, the optimality Bellman operator contains a max operator, which is non linear and, therefore, it has different features. In addition, it's possible to use hybrid methods between pure value iteration and pure policy iteration.
