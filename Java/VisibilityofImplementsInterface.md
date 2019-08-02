The implementation methods can't be static. Also, since interface methods are implicitly public, they must be declared public, regardless of the containing class's visibility. Try not doing so and it will fail to compile. This is certainly the reason it is declared public here -- it can't not be.

This is true regardless of whether the containing class is static or public. Here, it could be either of those things and the method inside would still have to be public and non-static.

Other methods that don't implement an interface could be private, and, logically probably should inside a private class as there would be no point in declaring it otherwise -- but it would be allowed by Java syntax.
