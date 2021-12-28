If you need to run the code in a distributed environment, it needs to be stateless. There should be no state in the code.

There can be no static instances in the class. Static instances hold application data and if a particular server goes down all the static data/state is lost. The app is left in an inconsistent state.

Rather, use a persistent memory like a Key-value store to hold the data and remove all the state/static variable from the class. This is why functional programming became so popular with distributed systems. The functions don’t retain any state.
