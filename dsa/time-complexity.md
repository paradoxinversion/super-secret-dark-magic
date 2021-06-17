Time complexity is a way of showing how runtime of a function increases with its inputs

constant: time remains the same despite input amt. O(1)
T = c = 0.115 (the number doesn't matter here.)
The fastest growing term is the number
the number is the coeeficient but not useful. so multiply it by 1-- 0.115 x 1. Then remove the first half of that to be left with 1 for O(1)
quadratic: time increases like a quadratic equation. O(n^2)

linear time: increases linearly as input increases. O(n) [n is the size of the input]
why do we know it's linear? math:
T=an+b = ???
a and b are constant things. they might change with various things like cpu load, system age, system speed, program language speed, etc. n is the amt of inputs.
first we need to find the fastest growing term between (an) and (b). B doesn't grow as input grows with (an), because of (n)'s value increasing.
next we need to take out the coefficient out of the fasted growing term. The coefficient is (a), leaving us with (n).
that leaves us with: T=an+b = O(n)

Another example: T = cn^2 + dn + e.
The fasted growing term is cn^2. Remove c as the coefficient.
T = cn^2 + dn + e = O(n^2)

We ultimate care about the higher bound of speed.

logarythmic time (such as with binary searches...)
