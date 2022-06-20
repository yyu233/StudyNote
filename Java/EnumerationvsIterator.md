1) The main difference between Iterator and Enumeration is removal of the element while traversing the collection. Iterator can remove the element during traversal of collection as it has remove() method. Enumeration does not have remove() method.

2) Enumeration is fail-safe in nature. It does not throw ConcurrentModificationException if Collection is modified during the traversal. Iterator is fail-fast in nature. It throws ConcurrentModificationException if a Collection is modified while iterating other than its own remove() method.

3) Enumeration is a legacy interface which is used for traversing Vector, Hashtable. Iterator is not a legacy interface. Iterator can be used for the traversal of HashMap, LinkedList, ArrayList, HashSet, TreeMap, TreeSet .
