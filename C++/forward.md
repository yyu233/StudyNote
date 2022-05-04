I think the explanation of std::forward as static_cast<T&&> is confusing. Our intuition for a cast is that it converts a type to some other type -- in this case it would be a conversion to an rvalue reference. It's not! So we are explaining one mysterious thing using another mysterious thing. This particular cast is defined by a table in Xeo's answer. But the question is: Why? So here's my understanding:

Suppose I want to pass you an std::vector<T> v that you're supposed to store in your data structure as data member _v. The naive (and safe) solution would be to always copy the vector into its final destination. So if you are doing this through an intermediary function (method), that function should be declared as taking a reference. (If you declare it as taking a vector by value, you'll be performing an additional totally unnecessary copy.)

void set(const std::vector<T> & v) { _v = v; }
This is all fine if you have an lvalue in your hand, but what about an rvalue? Suppose that the vector is the result of calling a function makeAndFillVector(). If you performed a direct assignment:

_v = makeAndFillVector();
the compiler would move the vector rather than copy it. But if you introduce an intermediary, set(), the information about the rvalue nature of your argument would be lost and a copy would be made.

set(makeAndFillVector()); // set will still make a copy
In order to avoid this copy, you need "perfect forwarding", which would result in optimal code every time. If you're given an lvalue, you want your function to treat it as an lvalue and make a copy. If you're given an rvalue, you want your function to treat it as an rvalue and move it.

Normally you would do it by overloading the function set() separately for lvalues and rvalues:

set(const std::vector<T> & lv) { _v = v; }
set(std::vector<T> && rv) { _v = std::move(rv); }
But now imagine that you're writing a template function that accepts T and calls set() with that T (don't worry about the fact that our set() is only defined for vectors). The trick is that you want this template to call the first version of set() when the template function is instantiated with an lvalue, and the second when it's initialized with an rvalue.

First of all, what should the signature of this function be? The answer is this:

template<class T>
void perfectSet(T && t);
Depending on how you call this template function, the type T will be somewhat magically deduced differently. If you call it with an lvalue:

std::vector<T> v;
perfectSet(v);
the vector v will be passed by reference. But if you call it with an rvalue:

perfectSet(makeAndFillVector());
the (anonymous) vector will be passed by rvalue reference. So the C++11 magic is purposefully set up in such a way as to preserve the rvalue nature of arguments if possible.

Now, inside perfectSet, you want to perfectly pass the argument to the correct overload of set(). This is where std::forward is necessary:

template<class T>
void perfectSet(T && t) {
    set(std::forward<T>(t));
}
Without std::forward the compiler would have to assume that we want to pass t by reference. To convince yourself that this is true, compare this code:

void perfectSet(T && t) {
    set(t);
    set(t); // t still unchanged
}
to this:

void perfectSet(T && t) {
    set(std::forward<T>(t));
    set(t); // t is now empty
}
If you don't explicitly forward t, the compiler has to defensively assume that you might be accessing t again and chose the lvalue reference version of set. But if you forward t, the compiler will preserve the rvalue-ness of it and the rvalue reference version of set() will be called. This version moves the contents of t, which means that the original becomes empty.
