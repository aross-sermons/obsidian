---
title: Python
parent:
  - "[[Cheat Sheet]]"
aliases: 
tags:
---

### Naming Conventions
**Variable Naming**
	Var
### Operators
**Math Operators** - Highest to Lowest Precedence

| Operator | Function       | Example       |
| -------- | -------------- | ------------- |
| \*\*     | Exponent       | 2 \*\* 3 = 8  |
| %        | Modulus        | 22 % 8 = 6    |
| //       | Int Division   | 22 // 8 = 2   |
| /        | Division       | 22 / 8 = 2.75 |
| \*       | Multiplication | 3 \* 3 = 9    |
| -        | Subtraction    | 5 - 2 = 3     |
| +        | Addition       | 2 + 2 = 4     |
**Augmented Assignment Operators**
	Any math operator can be used in front of an = as an augment.
	Ex: `var //= 1` is the same as `var = var // 1`

**Walrus Operator**
	The Walrus Operator `:=` allows assignment of variables within an expression while returning the value of the variable.
	Ex: `print(mystring:="hello") # 'hello'`

### String Manipulation
**String Concatenation**
	The `+` operator is not needed, just a space.
	Ex: `print("Andrew" "Savannah") # 'AndrewSavannah'`
**String Multiplication**
	The `*` operator can be used to repeat a string.
	Ex: `print("Andrew" * 2) # AndrewAndrew`