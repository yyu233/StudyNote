Continuous deployment#
Continuous deployment is a pain in monolithic applications because even a minor code change in a layer necessitates a re-deployment of the entire application.

Regression testing#
The downside of this is that we need a thorough regression testing of the entire application after the deployment is done because the layers are tightly coupled with each other. A change in one layer impacts the other layers significantly.

Single points of failure#
Monolithic applications have a single point of failure. If any of the layers has a bug, it can take down the entire application.

Scalability issues#
Flexibility and scalability are a challenge in monolith apps because a change in one layer often necessitates a change and testing in all the layers. As the code size increases, things might get a bit tricky to manage.

Cannot leverage heterogeneous technologies#
Building complex applications with a monolithic architecture are tricky because using heterogeneous technologies is difficult in a single codebase due to compatibility issues.

It is tricky to use Java and NodeJS together in a single codebase, and when I say tricky, I am being generous. I am not sure if it is even possible.

Not cloud-ready, hold state#
Generally, monolithic applications are not cloud-ready because they hold state in the static variables. An application to be cloud-native, to work smoothly, and to be consistent on the cloud has to be distributed and stateless.
