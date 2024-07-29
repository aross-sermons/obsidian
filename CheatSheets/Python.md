---
title: Python
parent:
  - "[[Cheat Sheet]]"
aliases: 
tags:
  - incomplete
---
### Naming Conventions
**All Naming Conventions**
- Internal - Prefix with \_
	- Ex: my_module -> \_my_module
- Packages - lower_with_under
- Modules - lower_with_under
- Classes - CapFirstLetter
- Exceptions - CapFirstLetter
- Functions - lower_with_under()
- Global/Class Constants - CAPS_WITH_UNDER
- Global/Class Variables - lower_with_under
- Instance Variables - lower_with_under
- Method Names - lower_with_under()
- Function/Method Parameters - lower_with_under
- Local Variables - lower_with_under
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