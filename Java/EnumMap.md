Like most collection implementations EnumMap is not synchronized. If multiple threads access an enum map concurrently, and at least one of the threads modifies the map, it should be synchronized externally. This is typically accomplished by synchronizing on some object that naturally encapsulates the enum map. If no such object exists, the map should be "wrapped" using the Collections.synchronizedMap(java.util.Map<K, V>) method. This is best done at creation time, to prevent accidental unsynchronized access:

     Map<EnumKey, V> m
         = Collections.synchronizedMap(new EnumMap<EnumKey, V>(...));
 
