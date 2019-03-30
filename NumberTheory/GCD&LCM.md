It is our common nature to try and simplify/generalize things by finding patterns. However, though it might me intuitive to try to apply the idea by extending it to the general case of n variables, it doesn't work in this case. I'll try to break up the reasoning behind the formula .

First we must understand how the formula of LCM(x,y) * GCD(x,y) = x * y might have come. To find LCM or GCD, one way is to break each of the numbers up into their prime factors. Let x = 84, y = 30

x = 2*2*3*7 = (2*3)*2*7

y = 2*3*5 = (2*3)*5

The portion in bracket is the common part. So we say that ok, 2*3, i.e. 6 should be able to divide both x and y and call it the GREATEST common divisor. Mind you, only 2 or only 3 are also common divisors of x and y, but not the GREATEST common divisors.

To find the LEAST common multiple, we take the GCD and multiply it by all the numbers which are left behind. So our LCM is (2*3)*2*7*5 = 420. I'm not describing the intuition behind this as it is simple and also not relevant directly.

So if you multiply x and y, you get 84*30 = (2*3*2*7)*(2*3*5) = (2*3)*((2*3)*2*7*5) = GCD(x,y)*LCM(x,y) = (2*3)*(2*3)*(2*7*5) = [common part raised to power 2, since it is repeated in both the numbers] * [the rest of the left over factors in all the numbers].

Now coming to your question, if you take one more variable z = 18 = (2*3)*3, GCD of all 3 numbers is common part (2*3), i.e., 6 and LCM is (2*3)*2*7*5*3, whatever that is.

Now x*y*z = (2*3)*(2*3)*(2*3)*(2*7*5*3) = [common part raised to power 3, since it is repeated in all 3 numbers] * [the rest of the left over factors in all the numbers]. But if you multiple GCD and LCM you will get only (2*3)*((2*3)*2*7*5*3) = (2*3)*(2*3)*(2*7*5*3), i.e. the common part is taken into consideration only twice instead of thrice.

However, it can also be the case when some of the factors between some numbers (not all, i.e. cannot be included in GCD) are common. In the general case of n variables, GDD(x[1],x[2],...x[n]) = c[1]c[2]..c[k] where each of c[i] 1<=i<=k exists once in all the numbers. LCM((x[1],x[2],...x[n]) = GCD(x[1],x[2],...x[n]) * ((h(p[1]) * h(p[2]) * ... h(p[l])) where each p[j], 1<=j<=l is a prime number in the list of left over factors not part of GCD and h(p[i]) is the highest power of p[i] present in any of them.

Now when we multiply LCM and GCD of n numbers, apart from loosing out on the factors of GCD on anything more than twice we also loose out on the factors which are partially common between some of the numbers and can only find the result of the highest powers which are present multiplied to the GCD.
