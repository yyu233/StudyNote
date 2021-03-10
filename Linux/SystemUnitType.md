* Service — A process or a group of processes, which systemd started based on a unit configuration file. Services encapsulate the specified processes so that they can be started and stopped as one set. Services are named in the following way:
name.service
Where name stands for the name of the service.
* Scope — A group of externally created processes. Scopes encapsulate processes that are started and stopped by arbitrary processes through the fork() function and then registered by systemd at runtime. For instance, user sessions, containers, and virtual machines are treated as scopes. Scopes are named as follows:
name.scope
Here, name stands for the name of the scope.
* Slice — A group of hierarchically organized units. Slices do not contain processes, they organize a hierarchy in which scopes and services are placed. The actual processes are contained in scopes or in services. In this hierarchical tree, every name of a slice unit corresponds to the path to a location in the hierarchy. The dash ("-") character acts as a separator of the path components. For example, if the name of a slice looks as follows:
parent-name.slice
it means that a slice called parent-name.slice is a subslice of the parent.slice. This slice can have its own subslice named parent-name-name2.slice, and so on.
```
There is one root slice denoted as:
-.slice
Service, scope, and slice units directly map to objects in the cgroup tree. When these units are activated, they map directly to cgroup paths built from the unit names. For example, the ex.service residing in the test-waldo.slice is mapped to the cgroup test.slice/test-waldo.slice/ex.service/.
Services, scopes, and slices are created manually by the system administrator or dynamically by programs. By default, the operating system defines a number of built-in services that are necessary to run the system. Also, there are four slices created by default:
-.slice — the root slice;
system.slice — the default place for all system services;
user.slice — the default place for all user sessions;
machine.slice — the default place for all virtual machines and Linux containers.
```
