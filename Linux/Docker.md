**Docker Container**: a runtime instance of docker image.  

**Docker Client**: a command-line tool used for engineering containers.   

**Docker Registry**: a public or private repo for docker images.  

**Dockerfile**: contains all the commands needed to build a docker image. 

### Container ##

Container allows you to package your applications and dependencies into one succinit manifest which can be verisoin controlled. The entire unit developers need to reason about becomes smaller, thus leads to greater agility and productivity. All this eases development, testing and deployment. 

### VM vs Container ###

* Memory Utilization    
Once a chunk of memory allocated to VM, that chunk of memory is blocked and cannot be reallocated.   
For container, CPU will allocate exactly the amount of memory required by the container. 

* Boot-up
VM takes more time since the guest OS needs to load up binaries and libraries.   
Container running on the host OS takes less time for boot-up.

[Good Read](https://www.edureka.co/blog/what-is-docker-container)






