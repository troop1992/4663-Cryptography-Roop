## Assignment 6 - Overview of Primality tests
### Tyler Roop
### Description:

This document observes 7 primality tests.

APR-CL algorithm
This algorithm is a deterministic algorithm that is improved APR algorithm. It can find if a number n is prime in time:
(log n)^(O(log log log n)
All that is needed is to find two numbers, s and t, that satisfy a set of conditions.
t is relatively small
s is greater than the square root of n
a^t is congruent to 1 (mod s) for all integers with gcd(a,s) = 1
and the prime factorization of t and s are known
Beyond this, the math gets too complicated for me to really understand as much, but I thought it would be interesting to discuss.

Baillie PSW Primality test
This algorithm uses the Fermat probable prime test to base 2 and the Lucas probable prime test to determine whether a number is prime or not. These two tests have pseudoprimes, but there are no known overlapping pseudoprimes between the two tests.
First, perform a base 2 Miller-Rabin primality test to determine whether it is composite.
Next, find the first D in the sequence 5, -7, 9, -11, 13, -15, … for which the Jacobi symbol (D/n) is -1. Set
P = 1 and Q = (1 – D) / 4
Finally, perform a strong Lucas probable prime test on n using parameters D, P, and Q. If n is also a strong Lucas probable prime, it is almost certainly prime

Lucas-Lehmer primality test
This test only applies to Mersenne numbers. That is, numbers that are one less than a power of 2.
Let Mp=2p-1 be the number we are testing. Then define a sequence {si} for all i >= 0 where si = 4 if i = 0 and si-12- 2 otherwise. Then Mp is prime if and only if sp-2 is congruent to 0 (mod Mp)
This test is used for the Great Internet Mersenne Prime Search

Lucas-Lehmer-Riesel test
This test was developed by Riesel using the previous test. 
First, define a sequence ui for all i > 0 by:
ui = ui-12 – 2 
N is prime if and only if un-2

Proth’s theorem
States that if p is a Proth number of the form k2n+1 with k odd and 2n > k and if there exists an integer a for which a ^ ((p-1)-2) is congruent to -1 (mod p) then p is prime.

Pepin’s test
This is a modification of the previous theorem that states: let Fn = 2^(2n) + 1 be the nth Fermat number. For n > 0, Fn is prime if and only if 3^((Fn- 1)/2) is congruent to -1 (mod Fn)

Pocklington theorem
This states that N is prime when N is and integer greater than 1 and there exists numbers a and p such that: aN-1 is congruent to 1 (mod N)
p is prime, p|N – 1  and p is greater than the sqrt(N) minus 1
and the gcd(aN-1)/p-1, N) = 1
