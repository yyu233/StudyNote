## Non-deterministic ##    

In a unit test, mock objects can simulate the behavior of complex, real objects and are therefore useful when a real object is impractical or impossible to incorporate into a unit test. If an object has any of the following characteristics, it may be useful to use a mock object in its place:

* the object supplies non-deterministic results (e.g. the current time or the current temperature);
* it has states that are difficult to create or reproduce (e.g. a network error);
* it is slow (e.g. a complete database, which would have to be initialized before the test);
* it does not yet exist or may change behavior;
* it would have to include information and methods exclusively for testing purposes (and not for its actual task).

For example, an alarm clock program which causes a bell to ring at a certain time might get the current time from a time service. To test this, the test must wait until the alarm time to know whether it has rung the bell correctly. If a mock time service is used in place of the real time service, it can be programmed to provide the bell-ringing time (or any other time) regardless of the real time, so that the alarm clock program can be tested in isolation


## TDD ## 

Programmers working with the test-driven development (TDD) method make use of mock objects when writing software. Mock objects meet the interface requirements of, and stand in for, more complex real ones; thus they allow programmers to write and unit-test functionality in one area without calling complex underlying or collaborating classes.

## Limitation ## 

The use of mock objects can closely couple the unit tests to the implementation of the code that is being tested. For example, many mock object frameworks allow the developer to check the order of and number of times that mock object methods were invoked by the real object being tested; subsequent refactoring of the code that is being tested could therefore cause the test to fail even though all mocked object methods still obey the contract of the previous implementation. This illustrates that unit tests should test a method's external behavior rather than its internal implementation. Over-use of mock objects as part of a suite of unit tests can result in a dramatic increase in the amount of maintenance that needs to be performed on the tests themselves during system evolution as refactoring takes place
