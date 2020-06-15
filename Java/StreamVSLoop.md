Streams are a more declarative style. Or a more expressive style. It may be considered better to declare your intent in code, than to describe how it's done:

 return people
     .filter( p -> p.age() < 19)
     .collect(toList());
... says quite clearly that you're filtering matching elements from a list, whereas:

 List<Person> filtered = new ArrayList<>();
 for(Person p : people) {
     if(p.age() < 19) {
         filtered.add(p);
     }
 }
 return filtered;
Says "I'm doing a loop". The purpose of the loop is buried deeper in the logic.

Streams are often terser. The same example shows this. Terser isn't always better, but if you can be terse and expressive at the same time, so much the better.

Streams have a strong affinity with functions. Java 8 introduces lambdas and functional interfaces, which opens a whole toybox of powerful techniques. Streams provide the most convenient and natural way to apply functions to sequences of objects.

Streams encourage less mutability. This is sort of related to the functional programming aspect -- the kind of programs you write using streams tend to be the kind of programs where you don't modify objects.

Streams encourage looser coupling. Your stream-handling code doesn't need to know the source of the stream, or its eventual terminating method.

Streams can succinctly express quite sophisticated behaviour. For example:

 stream.filter(myfilter).findFirst();
Might look at first glance as if it filters the whole stream, then returns the first element. But in fact findFirst() drives the whole operation, so it efficiently stops after finding one item.

Streams provide scope for future efficiency gains. Some people have benchmarked and found that single-threaded streams from in-memory Lists or arrays can be slower than the equivalent loop. This is plausible because there are more objects and overheads in play.

But streams scale. As well as Java's built-in support for parallel stream operations, there are a few libraries for distributed map-reduce using Streams as the API, because the model fits.

Disadvantages?

Performance: A for loop through an array is extremely lightweight both in terms of heap and CPU usage. If raw speed and memory thriftiness is a priority, using a stream is worse.

Familiarity.The world is full of experienced procedural programmers, from many language backgrounds, for whom loops are familiar and streams are novel. In some environments, you want to write code that's familiar to that kind of person.

Cognitive overhead. Because of its declarative nature, and increased abstraction from what's happening underneath, you may need to build a new mental model of how code relates to execution. Actually you only need to do this when things go wrong, or if you need to deeply analyse performance or subtle bugs. When it "just works", it just works.

Debuggers are improving, but even now, when you're stepping through stream code in a debugger, it can be harder work than the equivalent loop, because a simple loop is very close to the variables and code locations that a traditional debugger works with.
