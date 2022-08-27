The introduction of the decltype type specifier enables a developer to obtain the type of the expression that the template function returns. Use the alternative function declaration syntax that is shown later, the auto keyword, and the decltype type specifier to declare a late-specified return type. The late-specified return type is determined when the declaration is compiled, instead of when it is coded.

The following prototype illustrates the syntax of an alternative function declaration. Note that the const and volatile qualifiers, and the throw exception specification are optional. The function_body placeholder represents a compound statement that specifies what the function does. As a best coding practice, the expression placeholder in the decltype statement should match the expression specified by the return statement, if any, in the function_body.

auto function_name ( parametersopt ) constopt volatileopt -> decltype( expression ) noexceptopt { function_body };

In the following code example, the late-specified return type of the myFunc template function is determined by the types of the t and u template arguments. As a best coding practice, the code example also uses rvalue references and the forward function template, which support perfect forwarding.

C++
```
//C++11
template<typename T, typename U>
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))
        { return forward<T>(t) + forward<U>(u); };

//C++14
template<typename T, typename U>
decltype(auto) myFunc(T&& t, U&& u)
        { return forward<T>(t) + forward<U>(u); };
 ```
