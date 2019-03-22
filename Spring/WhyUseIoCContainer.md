## Advantages ##
1. Dependdency Chain

Something i dislike about not using IoC containers is when I end up with long dependency chains. You might have a Service which needs a DataRepository which in turn needs a ConnectionHelper. This would require 3 classes to be created and injected. Injections within injections can create some long lines of code. Using a container you would just go something like container.Resolve<IService>(); (Which
should happen behind the scenes in your program). This is a huge advantage when it comes to reading the code. You want a service - then you just need to request it (yes it is not that simple - I will get to the configuration later).

2. Centralized Configuration

One of the features I have enjoyed the most about IoC containers is lifetime management. Overly simplify it, and it comes down to whether to create a new instance when requested or keep returning the same.

## Disadvantages ##

1. Hard to figure out the flow in the application. As in, what is the actual implemtation of the dependency you are looking at?
2. No build errors - requires some way of testing dependencies together (yes not unit tests)

[Good Read](https://peterdaugaardrasmussen.com/2017/07/30/advantages-of-ioc-containers-and-why-we-use-them/) 
