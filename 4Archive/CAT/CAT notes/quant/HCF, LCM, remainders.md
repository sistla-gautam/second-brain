# types of questions
---
###### number when divided by x, y, z leaves remainders a, b, c respectively

the questions will ask us to find the numbers that will do the following conditions
- leave a remainder of 2 when divided by 3
- leave a remainder of 1 when divided by 4
- leave a remainder of 3 when divided by 7

to solve this type of question, we take the numbers which will satisfy condition 3
3, 10, 17, 24, 31 ...

now, we check from these numbers that will satisfy condition 2
we get
17, 45, 73, 101 ...

==the first number will be obtained by observation. the gap is obtained by the LCM of the 2 numbers (7, 4 = 28)==

now we check from these numbers that will satisfy the condition 1
we get
17, 101, 185 ...

therefore, we get the general formula as 17 + 84p
using these, we can find the required numbers

---
###### find the remainder of a number with repeating digits

for this, we need to check for the following conditions. if the conditions are met, then we can use a generalized formula to find the remainder

the conditions are
- symmetry of the number - the number of repetitions is a perfect number
- $10^n$ such that when divided by the divisor, we get 1 as the remainder, and thus expand in 'n' digits

if both the conditions are satisfied, then we can find the remainder by

R = $\frac{repeating\space unit \times nunber\space Of\space repetitions}{divisor}$

if the number is 464646.....240 digits and the divisor is 999, then we get the following

the number $10^6$ will leave a remainder of 1, when divided by 999. thus we expand in 6 digits
number of repetitions will be 40
remainder = 6 * 40 / 999 => 444

---
###### greatest number to divide any 3 numbers leaving the same remainder
3 different numbers will be given
we need to find the greatest number which will divide the three numbers leaving the same remainder in each

to solve this, we take the HCF of the difference between pairs of two values
- if the numbers are 25, 60, 130
- we need to find the HCF of (60-25), (130-60), (130-25)
- the HCF of 35, 70, 105 is ==35==