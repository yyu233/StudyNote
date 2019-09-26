These constants have nothing to do with sign. This makes more sense if you consider a double as a composite of three parts: Sign, Exponent and Mantissa. Double.MIN_VALUE is actually the smallest value Mantissa can assume when the Exponent is at minimun value before a flush to zero occurs. Likewise MAX_VALUE can be understood as the largest value Mantissa can assume when the Exponent is at maximum value before a flush to infinity occurs.

A more descriptive name for these two could be Largest Absolute (add non-zero for verbositiy) and Smallest Absolute value (add non-infinity for verbositiy).

Check out the IEEE 754 (1985) standard for details. There is a revised (2008) version, but that only introduces more formats which aren't even supported by java (strictly speaking java even lacks support for some mandatory features of IEEE 754 1985, like many other high level languages).
