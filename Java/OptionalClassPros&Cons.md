Advantages    
Doing this reduces the presence of nulls in your code base, although it does not eradicate them. But that is not even the main point. There are other important advantages:

Clarifies Intent      
Using Optional clearly expresses that the variable is, well, optional. Any reader of your code or consumer of your API will be beaten over the head with the fact that there might be nothing there and that a check is necessary before accessing the value.

Removes Uncertainty     
Without Optional the meaning of a null occurrence is unclear. It could be a legal representation of a state (see Map.get) or an implementation error like a missing or failed initialization.

This changes dramatically with the persistent use of Optional. Here, already the occurrence of null signifies the presence of a bug. (Because if the value were allowed to be missing, an Optional would have been used.) This makes debugging a null pointer exception much easier as the question of the meaning of this null is already answered.

More Null Checks    
Now that nothing can be null anymore, this can be enforced everywhere. Whether with annotations, assertions or plain checks, you never have to think about whether this argument or that return type can be null. It can't!

Disadvantages   
Of course, there is no silver bullet...

Performance     
Wrapping values (especially primitives) into an extra instance can degrade performance. In tight loops this might become noticeable or even worse.

Note that the compiler might be able to circumvent the extra reference for short lived lifetimes of Optionals. In Java 10 value types might further reduce or remove the penalty.

Serialization     
Optional is not serializable but a workaround is not overly complicated.

Invariance      
Due to the invariance of generic types in Java, certain operations become cumbersome when the actual value type is pushed into a generic type argument. An example is given here (see "Parametric polymorphism").
