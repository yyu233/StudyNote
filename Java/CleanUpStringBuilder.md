There are basically two alternatives, using setLength(0) to reset the StringBuilder or creating a new one in each iteration. Both can have pros and cons depending on the usage.

If you know the expected capacity of the StringBuilder beforehand, creating a new one each time should be just as fast as setting a new length. It will also help the garbage collector, since each StringBuilder will be relatively short-lived and the gc is optimized for that.

When you don't know the capacity, reusing the same StringBuilder might be faster. Each time you exceed the capacity when appending, a new backing array has to be allocated and the previous content has to be copied. By reusing the same StringBuilder, it will reach the needed capacity after some iterations and there won't be any copying thereafter.
