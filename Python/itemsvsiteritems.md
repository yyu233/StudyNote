items() creates the items all at once and returns a list. iteritems() returns a generator--a generator is an object that "creates" one item at a time every time next() is called on it.

 When using items() method, the iteration needs to be completed and stored in-memory before for loop can begin iterating.
 Use iteritems() to iterate over large dictionary
