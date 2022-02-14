The interface{} type, the empty interface, is the source of much confusion. The interface{} type is the interface that has no methods. Since there is no implements keyword, all types implement at least zero methods, and satisfying an interface is done automatically, all types satisfy the empty interface. That means that if you write a function that takes an interface{} value as a parameter, you can supply that function with any value. So, this function:
```
func DoSomething(v interface{}) {
   // ...
}
```
will accept any parameter whatsoever.

Here’s where it gets confusing: inside of the DoSomething function, what is v’s type? Beginner gophers are led to believe that “v is of any type”, but that is wrong. v is not of any type; it is of interface{} type. Wait, what? When passing a value into the DoSomething function, the Go runtime will perform a type conversion (if necessary), and convert the value to an interface{} value. All values have exactly one type at runtime, and v’s one static type is interface{}.
