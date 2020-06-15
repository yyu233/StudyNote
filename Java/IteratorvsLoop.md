First of all, there are 2 kinds of for loops, which behave very differently. One uses indices:

for (int i = 0; i < list.size(); i++) {
    Thing t = list.get(i);
    ...
}
This kind of loop isn't always possible. For example, Lists have indices, but Sets don't, because they're unordered collections.

The other one, the foreach loop uses an Iterator behind the scenes:

for (Thing thing : list) {
    ...
}
This works with every kind of Iterable collection (or array)

And finally, you can use an Iterator, which also works with any Iterable:

for (Iterator<Thing> it = list.iterator(); it.hasNext(); ) {
    Thing t = it.next();
    ...
} 
So you in fact have 3 loops to compare.

You can compare them in different terms: performance, readability, error-proneness, capability.

An Iterator can do things that a foreach loop can't. For example, you can remove elements while you're iterating, if the iterator supports it:

for (Iterator<Thing> it = list.iterator(); it.hasNext(); ) {
    Thing t = it.next();
    if (shouldBeDeleted(thing) {
        it.remove();
    }
} 
Lists also offer iterators that can iterate in both directions. A foreach loop only iterates from the beginning to an end.

But an Iterator is more dangerous and less readable. When a foreach loop is all you need, it's the most readable solution. With an iterator, you could do the following, which would be a bug:

for (Iterator<Thing> it = list.iterator(); it.hasNext(); ) {
    System.out.println(it.next().getFoo());
    System.out.println(it.next().getBar());
} 
A foreach loop doesn't allow for such a bug to happen.

Using indices to access elements is slightly more efficient with collections backed by an array. But if you change your mind and use a LinkedList instead of an ArrayList, suddenly the performance will be awful, because each time you access list.get(i), the linked list will have to loop though all its elements until the ith one. An Iterator (and thus the foreach loop) doesn't have this problem. It always uses the best possible way to iterate through elements of the given collection, because the collection itself has its own Iterator implementation.

My general rule of thumb is: use the foreach loop, unless you really need capabilities of an Iterator. I would only use for loop with indices with arrays, when I need access to the index inside the loop.

When you use an Iterator to remove one or more elements in a collection, this is safe to do. When you use a for-each or for loop, removing is either not allowed or causes a bug because when removing while looping over the collection the indexes of each element in the collection changes. Therefore you should use a reverse for loop, or use an iterator to prevent introducing a bug. 

