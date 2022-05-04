Computers store floating point numbers in binary, not decimal.

Many numbers that look ordinary in decimal, such as 0.3, have no exact representation of finite length in binary.
Therefore, the compiler picks the closest number that has an exact binary representation, just like you write 0.33333 for 1⁄3.

If you add many floating-point numbers, these tiny difference add up, and you get unexpected results.
