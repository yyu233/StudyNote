The macro also supports to pass the tokens to the macro to concatenate tokens using the special operator “##” which is known as the token pasting operator. Let us see an example:
Example:
```
#include <stdio.h>
#define concate(p, q) p##q
intmain()
{
printf("%d ", concate(56, 78));
}
```
