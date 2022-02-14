Another subtlety of interfaces is that an interface definition does not prescribe whether an implementor should implement the interface using a pointer receiver or a value receiver. When you are given an interface value, there’s no guarantee whether the underlying type is or isn’t a pointer. In our previous example, we defined all of our methods on value receivers, and we put the associated values into the Animal slice. Let’s change this and make the Cat’s Speak() method take a pointer receiver:
```
func (c *Cat) Speak() string {
    return "Meow!"
}
```
If you change that one signature, and you try to run the same program exactly as-is (http://play.golang.org/p/TvR758rfre), you will see the following error:
```
prog.go:40: cannot use Cat literal (type Cat) as type Animal in array element:
    Cat does not implement Animal (Speak method requires pointer receiver)
```
This error message is a bit confusing at first, to be honest. What it’s saying is not that the interface Animal demands that you define your method as a pointer receiver, but that you have tried to convert a Cat struct into an Animal interface value, but only *Cat satisfies that interface. You can fix this bug by passing in a *Cat pointer to the Animal slice instead of a Cat value, by using new(Cat) instead of Cat{} (you could also say &Cat{}, I simply prefer the look of new(Cat)):
```
animals := []Animal{Dog{}, new(Cat), Llama{}, JavaProgrammer{}}
```
now our program works again:http://play.golang.org/p/x5VwyExxBM

Let’s go in the opposite direction: let’s pass in a *Dog pointer instead of a Dog value, but this time we won’t change the definition of the Dog type’s Speak method:
```
animals := []Animal{new(Dog), new(Cat), Llama{}, JavaProgrammer{}}
````
This also works (http://play.golang.org/p/UZ618qbPkj), but recognize a subtle difference:  we didn’t need to change the type of the receiver of the Speak method. This works because a pointer type can access the methods of its associated value type, but not vice versa. That is, a *Dog value can utilize the Speak method defined on Dog, but as we saw earlier, a Cat value cannot access the Speak method defined on *Cat.

That may sound cryptic, but it makes sense when you remember the following: everything in Go is passed by value. Every time you call a function, the data you’re passing into it is copied. In the case of a method with a value receiver, the value is copied when calling the method. This is slightly more obvious when you understand that a method of the following signature:
```
func (t T)MyMethod(s string) {
    // ...
}
```
is a function of type func(T, string); method receivers are passed into the function by value just like any other parameter.

Any changes to the receiver made inside of a method defined on a value type (e.g., func (d Dog) Speak() { ... }) will not be seen by the caller because the caller is scoping a completely separate Dog value. Since everything is passed by value, it should be obvious why a *Cat method is not usable by a Cat value; any one Cat value may have any number of *Cat pointers that point to it. If we try to call a *Cat method by using a Cat value, we never had a *Cat pointer to begin with.
