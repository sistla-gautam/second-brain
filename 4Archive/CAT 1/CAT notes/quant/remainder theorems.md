
#### cyclicity
- we use the last digit cyclicity to determine the remainder of the number
- useful for small values
- not feasible for large values

#### if the divisor is a prime number
- in such a case, we can make use of the following formula
- $a^{p-1}mod p = 1$
- we now split the number into such a way, that we can reduce it to a smaller values to determine the remainder
- if we need to calculate the remainder of the $3^{205}mod 5$, then we can reduce it down to the following way
	- $3^{205}mod 5$ = $3^{6*33}mod5$.$3^7mod5$ = 1.$3^7mod5$
	- this will reduce the number of required values to be calculated

#### if the divisor is not a prime, but the numbers are co prime
- we need to make use of the totient function
- $\phi(n) = n(1-\frac{1}{p})(1-\frac{1}{q})...$ where, $n=p^a.q^b.r^c...$
- we now have the formula
	- $a^{\phi(n)}mod n = 1$
	- in the similar way as the previous method, we will reduce the required value to its lowest possible value to make calculation easier

#### wilsons theorem
- useful if the number to be calculating the mod of is in factorials
- it says
	- $(n-1)!mod n = 1$
	- use this to make calculation simpler

#### Chinese reminder theorem
- useful when we can split the divisor into 2 easy to calculate factors - a,b as long as a and b are co prime
- to calculate use the photo below
![[Pasted image 20241121200147.png]]