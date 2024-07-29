---
title: Concatenation
parent:
  - "[[Coding Challenge]]"
aliases: 
tags:
  - incomplete
  - wip
---
### Concatenation
Combining two things into one.
### Challenge #1 - Concatenate Integers
**Method #1** - Horner's Scheme
1. Multiply the first integer by 10.
2. Add the second integer.
	Only works if the second integer is a single digit.
**Method #2** - Horner's Scheme + Reverse
1. If either integer is more than one digit, break down to an array of single digits.
	1. Find value of first digit.
	2. Add first digit to array, subtract first digit+10\*\*exponent.
	3. Repeat.