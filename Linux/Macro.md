## Macro Syntax ## 

Define Macro: ``` %define <name> [(opt)] <body> ```    

A macro without opt is simple substituion (Recursive macro expansion is performed).  

A macro with op is paramterized. Options are passed to gettopt(3) for preposessing.   

Inside macro, we can use special macros to access parameters.   

|Macro|Holds|
|-----|-----|
|%0| the name of the macro being invoked|
|%*|all arguments excluding flags|
|%**|all arguments including flags|
|%#|number of arguments|
|%1|the first parameter|
|%2|the second parameter|
|%3|the third parameter|
|%{-f}|if f present at invocation, flag f iteself|
|%{-f*}|if f present at invocation, the argument to flag f|
|%{-f:text}|if f present at invocation, the text| 

