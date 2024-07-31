---
title: Integer Manipulation Challenge
parent:
  - "[[Coding Challenge]]"
aliases: 
tags:
  - incomplete
  - wip
---
### Integer Manipulation Challenge
Challenges for manipulating integers.
### Challenge #1 - Concatenate Integers
**Method #1** - Horner's Scheme
1. Multiply the first integer by 10.
2. Add the second integer.
	Only works if the second integer is a single digit.
**Method #2** - Horner's Scheme + Single Digit Array
1. If the second integer is more than one digit, break down to an array of single digits.
	1. See Challenge #2.
2. Add each integer in the array to the first integer.
**Method #3** - Type Casting
1. Cast both integers to strings.
2. Perform string concatenation.
3. Cast single string to integer.
### Challenge #2 - Integer to Single Digit Array
**Method #1** - Lowest to Highest
1. Get the lowest digit using modulus `n % 10`.
2. Append that digit to a list.
3. Remove the lowest digit using floor division `n // 10`.
4. Repeat 1-3 until `n <= 0`.
5. Reverse array.
**Method #2** - Type Casting
1. Cast integer to string.
2. Add each char to an array while type casting to integer.
