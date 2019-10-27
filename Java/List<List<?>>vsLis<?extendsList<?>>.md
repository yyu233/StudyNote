Fundamentally, List<List<?>> and List<? extends List<?>> have distinct type arguments.

It's actually the case that one is a subtype of the other, but first let's learn more about what they mean individually.

Understanding semantic differences
Generally speaking, the wildcard ? represents some "missing information". It means "there was a type argument here once, but we don't know what it is anymore". And because we don't know what it is, restrictions are imposed on how we can use anything that refers to that particular type argument.

For the moment, let's simplify the example by using List instead of Map.

A List<List<?>> holds any kind of List with any type argument. So i.e.:

```
List<List<?>> theAnyList = new ArrayList<List<?>>();

// we can do this
theAnyList.add( new ArrayList<String>() );
theAnyList.add( new LinkedList<Integer>() );

List<?> typeInfoLost = theAnyList.get(0);
// but we are prevented from doing this
typeInfoLost.add( new Integer(1) );
```
We can put any List in theAnyList, but by doing so we have lost knowledge of their elements.

When we use ? extends, the List holds some specific subtype of List, but we don't know what it is anymore. So i.e.:

```
List<? extends List<Float>> theNotSureList =
    new ArrayList<ArrayList<Float>>();

// we can still use its elements
// because we know they store Float
List<Float> aFloatList = theNotSureList.get(0);
aFloatList.add( new Float(1.0f) );

// but we are prevented from doing this
theNotSureList.add( new LinkedList<Float>() );
```

It's no longer safe to add anything to the theNotSureList, because we don't know the actual type of its elements. (Was it originally a List<LinkedList<Float>>? Or a List<Vector<Float>>? We don't know.)

We can put these together and have a List<? extends List<?>>. We don't know what type of List it has in it anymore, and we don't know the element type of those Lists either. So i.e.:
```
List<? extends List<?>> theReallyNotSureList;

// these are fine
theReallyNotSureList = theAnyList;
theReallyNotSureList = theNotSureList;

// but we are prevented from doing this
theReallyNotSureList.add( new Vector<Float>() );
// as well as this
theReallyNotSureList.get(0).add( "a String" );
```

We've lost information both about theReallyNotSureList, as well as the element type of the Lists inside it.

(But you may note that we can assign any kind of List holding Lists to it...)


So to break it down:
```
//   ┌ applies to the "outer" List
//   ▼
List<? extends List<?>>
//                  ▲
//                  └ applies to the "inner" List
The Map works the same way, it just has more type parameters:

//  ┌ Map K argument
//  │  ┌ Map V argument
//  ▼  ▼
Map<?, ? extends List<?>>
//                    ▲
//                    └ List E argument
```
Why ? extends is necessary
You may know that "concrete" generic types have invariance, that is, List<Dog> is not a subtype of List<Animal> even if class Dog extends Animal. Instead, the wildcard is how we have covariance, that is, List<Dog> is a subtype of List<? extends Animal>.

```
// Dog is a subtype of Animal
class Animal {}
class Dog extends Animal {}

// List<Dog> is a subtype of List<? extends Animal>
List<? extends Animal> a = new ArrayList<Dog>();

// all parameterized Lists are subtypes of List<?>
List<?> b = a;
```
So applying these ideas to a nested List:

List<String> is a subtype of List<?> but List<List<String>> is not a subtype of List<List<?>>. As shown before, this prevents us from compromising type safety by adding wrong elements to the List.
List<List<String>> is a subtype of List<? extends List<?>>, because the bounded wildcard allows covariance. That is, ? extends allows the fact that List<String> is a subtype of List<?> to be considered.
List<? extends List<?>> is in fact a shared supertype:

```
     List<? extends List<?>>
          ╱          ╲
List<List<?>>    List<List<String>>
```
In review
Map<Integer, List<String>> accepts only List<String> as a value.
Map<?, List<?>> accepts any List as a value.
Map<Integer, List<String>> and Map<?, List<?>> are distinct types which have separate semantics.
One cannot be converted to the other, to prevent us from doing modifications in an unsafe way.
Map<?, ? extends List<?>> is a shared supertype which imposes safe restrictions:

```
        Map<?, ? extends List<?>>
             ╱          ╲
Map<?, List<?>>     Map<Integer, List<String>>
```

How the generic method works
By using a type parameter on the method, we can assert that List has some concrete type.

static <E> void test(Map<?, List<E>> m) {}
This particular declaration requires that all Lists in the Map have the same element type. We don't know what that type actually is, but we can use it in an abstract manner. This allows us to perform "blind" operations.

For example, this kind of declaration might be useful for some kind of accumulation:

```
static <E> List<E> test(Map<?, List<E>> m) {
    List<E> result = new ArrayList<E>();

    for(List<E> value : m.values()) {
        result.addAll(value);
    }

    return result;
}
```
We can't call put on m because we don't know what its key type is anymore. However, we can manipulate its values because we understand they are all List with the same element type.

Just for kicks
Another option which the question does not discuss is to have both a bounded wildcard and a generic type for the List:

static <E> void test(Map<?, ? extends List<E>> m) {}
We would be able to call it with something like a Map<Integer, ArrayList<String>>. This is the most permissive declaration, if we only cared about the type of E.

We can also use bounds to nest type parameters:
```
static <K, E, L extends List<E>> void(Map<K, L> m) {
    for(K key : m.keySet()) {
        L list = m.get(key);
        for(E element : list) {
            // ...
        }
    }
}
```
This is both permissive about what we can pass to it, as well as permissive about how we can manipulate m and everything in it.
