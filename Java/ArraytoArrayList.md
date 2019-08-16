## Array to ArrayList ##

````
static <T> List<T> arrayToList(final T[] array) {
    final List<T> l = new ArrayList<T>(array.length);
    
    for (final T s: array) {
        l.add(s);
    }
    
    return l;
}
```
