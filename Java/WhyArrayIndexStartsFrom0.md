So, 0-based index allows array[index] to be implemented as *(array + index). If index were 1-based, compiler would need to generate *(array + index - 1), and this "-1" would hurt the performance. Rather than subtracting 1, you should use the address of the array-1 as the base address. That eliminates the runtime subtraction. When you're writing a compiler, those extra instructions matter a lot. The compiler will be used to generate thousands of programs, each of which may be used thousands of times, and that extra 1 instruction may occur in several lines inside an n squared loop. It can add up to billions of wasted cycles.