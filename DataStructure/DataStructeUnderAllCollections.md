```
As the java sources provide all the implementation details, I'll just expose a bunch of the most used collections:

java.util.ArrayList<E>
The implementation of ArrayList falls back internally to an array of Object.

/**
 * The array buffer into which the elements of the ArrayList are stored.
 * The capacity of the ArrayList is the length of this array buffer. Any
 * empty ArrayList with elementData == DEFAULTCAPACITY_EMPTY_ELEMENTDATA
 * will be expanded to DEFAULT_CAPACITY when the first element is added.
 */
transient Object[] elementData; // non-private to simplify nested class access
Since arrays have fixed size, ArrayList at each add call, recreates, if necessary elementData via native calls to System::arrayCopy.

java.util.LinkedList<E>
LinkedLists work over object references rather than arrays. All items E are stored into instances of the internal class Node<E>:

private static class Node<E> {
    E item;
    Node<E> next;
    Node<E> prev;

    Node(Node<E> prev, E element, Node<E> next) {
        this.item = element;
        this.next = next;
        this.prev = prev;
    }
}
where each Node keeps a pointer to its next and previous siblings.

A LinkedList will only keep a reference to its first and last elements, ergo random access is not supported:

/**
 * Pointer to first node.
 * Invariant: (first == null && last == null) ||
 *            (first.prev == null && first.item != null)
 */
transient Node<E> first;

/**
 * Pointer to last node.
 * Invariant: (first == null && last == null) ||
 *            (last.next == null && last.item != null)
 */
transient Node<E> last;
java.util.HashMap<K,V>
They store keys and values into an internal bundle class Node<K,V> extends Map.Entry<K,V>.

Nodes are stored via the function call HashMap::putVal into a Node array:

/**
 * The table, initialized on first use, and resized as
 * necessary. When allocated, length is always a power of two.
 * (We also tolerate length zero in some operations to allow
 * bootstrapping mechanics that are currently not needed.)
 */
transient Node<K,V>[] table;
Additionally, Hashmaps use a EntrySet extends AbstractSet<Map.Entry<K,V>> collection that constantly reflects the elements in table.

/**
 * Holds cached entrySet(). Note that AbstractMap fields are used
 * for keySet() and values().
 */
transient Set<Map.Entry<K,V>> entrySet;
entrySet is then exposed as an iterable collection:

for ( Map.Entry<String, Integer> entry : this.myMap.entrySet() ) { /* ... */ }
java.util.HashSet<E>
Funny thing is HashSet<T> uses an HashMap<T, Object> which, as we have seen is backed by a java.util.Set<T> again.

private transient HashMap<E,Object> map;
You'll see the body of HashSet is kind of limited compared to those of other java data structures as most of its operations are just a fallback to its internal HashMap structure.

E.g:

HashSet::add

public boolean add(E e) {
    return map.put(e, PRESENT)==null;
}
HashSet::iterator

public Iterator<E> iterator() {
    return map.keySet().iterator();
}
```
