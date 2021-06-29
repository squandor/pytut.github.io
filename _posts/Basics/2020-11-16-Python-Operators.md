---
layout: page
#
# Content
#
subheadline: "Python Operators"
title: "Python Operators"
categories:
  - Basics
tags:
  - Python
  - Basics
  - Examples
#
# Styling
#
header: no
mediaplayer: false
comments: true
---
Great. Now you know the syntax of the basic data types and built-in data structures in Python, so let's start diving into operators in Python. They are essential to perform operations and to form expressions.
Arithmetic Operators in Python
These operators are: 
Addition: +
>>> 5 + 6
11

>>> 0 + 6
6

>>> 3.4 + 5.7
9.1

>>> "Hello" + ", " + "World"
'Hello, World'

>>> True + False
1
When they are strings, this operator concatenates the strings and when they are Boolean values, it performs a particular operation. 
In Python, True is equivalent to 1 and False is equivalent to 0. This is why the result is 1 + 0 = 1
Subtraction: -
>>> 5 - 6
-1

>>> 10 - 3
7

>>> 5 - 6
-1

>>> 4.5 - 5.6 - 2.3
-3.3999999999999995

>>> 4.5 - 7
-2.5

>>> - 7.8 - 6.2
-14.0
Multiplication: *
>>> 5 * 6
30

>>> 6 * 7
42

>>> 10 * 100
1000

>>> 4 * 0
0

>>> 3.4 *6.8
23.119999999999997

>>> 4 * (-6)
-24

>>> (-6) * (-8)
48

>>> "Hello" * 4
'HelloHelloHelloHello'

>>> "Hello" * 0
''

>>> "Hello" * -1
''
Exponentiation: **
>>> 6 ** 8
1679616

>>> 5 ** 2
25

>>> 4 ** 0
1

>>> 16 ** (1/2)
4.0

>>> 16 ** (0.5)
4.0

>>> 125 ** (1/3)
4.999999999999999

>>> 4.5 ** 2.3
31.7971929089206

>>> 3 ** (-1)
0.3333333333333333
Division: /
>>> 25 / 5
5.0

>>> 3 / 6
0.5

>>> 0 / 5
0.0

>>> 2467 / 4673
0.5279263856195163

>>> 1 / 2
0.5

>>> 4.5 / 3.5
1.2857142857142858

>>> 6 / 7
0.8571428571428571

>>> -3 / -4
0.75

>>> 3 / -4
-0.75

>>> -3 / 4
-0.75
If you try to divide by 0, you will get a ZeroDivisionError:
>>> 5 / 0
Traceback (most recent call last):
  File "<pyshell#109>", line 1, in <module>
    5 / 0
ZeroDivisionError: division by zero
Integer Division: //
This operator returns an integer if the operands are integers. If they are floats, the result will be a float with .0 as the decimal part because it truncates the decimal part.
>>> 5 // 6
0

>>> 8 // 2
4

>>> -4 // -5
0

>>> -5 // 8
-1

>>> 0 // 5
0

>>> 156773 // 356
440
Modulo: %
>>> 1 % 5
1

>>> 2 % 5
2

>>> 3 % 5
3

>>> 4 % 5
4

>>> 5 % 5
0

>>> 5 % 8
5

>>> 3 % 1
0

>>> 15 % 3
0

>>> 17 % 8
1

>>> 2568 % 4
0

>>> 245 % 15
5

>>> 0 % 6
0

>>> 3.5 % 2.4
1.1

>>> 6.7 % -7.8
-1.0999999999999996

>>> 2.3 % 7.5
2.3
Comparison Operators
These operators are:
Greater than: >Greater than or equal to: >= Less than: <Less than or equal to: <= Equal to: == Not Equal to: !=
These comparison operators make expressions that evaluate to either True or False. Here we have are some examples:
>>> 5 > 6
False

>>> 10 > 8
True

>>> 8 > 8
False

>>> 8 >= 5
True

>>> 8 >= 8
True

>>> 5 < 6
True

>>> 10 < 8
False

>>> 8 < 8
False

>>> 8 <= 5
False

>>> 8 <= 8
True

>>> 8 <= 10
True

>>> 56 == 56
True

>>> 56 == 78
False

>>> 34 != 59
True

>>> 67 != 67
False
We can also use them to compare strings based on their alphabetical order:
>>> "Hello" > "World"
False
>>> "Hello" >= "World"
False
>>> "Hello" < "World"
True
>>> "Hello" <= "World"
True
>>> "Hello" == "World"
False
>>> "Hello" != "World"
True
We typically use them to compare the values of two or more variables:
>>> a = 1
>>> b = 2

>>> a < b
True

>>> a <= b
True

>>> a > b
False

>>> a >= b
False

>>> a == b
False

>>> a != b
True
Comparison Operator Chaining
In Python, we can use something called "comparison operator chaining" in which we chain the comparison operators to make more than one comparison more concisely. 
For example, this checks if a is less than b and if b is less than c:
a < b < c
Here we have some examples:
>>> a = 1
>>> b = 2
>>> c = 3

>>> a < b < c
True

>>> a > b > c
False

>>> a <= b <= c
True

>>> a >= b >= c
False

>>> a >= b > c
False

>>> a <= b < c
True
Logical Operators
There are three logical operators in Python: and, or, and not. Each one of these operators has its own truth table and they are essential to work with conditionals.
The and operator:
>>> True and True
True

>>> True and False
False

>>> False and True
False

>>> False and False
False
The or operator:
>>> True or True
True

>>> True or False
True

>>> False or True
True

>>> False or False
False
The not operator:
>>> not True
False

>>> not False
True
These operator are used to form more complex expressions that combine different operators and variables.
For example:
>>> a = 6
>>> b = 3

>>> a < 6 or b > 2
True

>>> a >= 3 and b >= 1
True

>>> (a + b) == 9 and b > 1
True

>>> ((a % 3) < 2) and ((a + b) == 3)
False
Assignment Operators
Assignment operators are used to assign a value to a variable. 
They are: =, +=, -=, *=, %=, /=, //=, **=
The = operator assigns the value to the variable.The other operators perform an operation with the current value of the variable and the new value and assigns the result to the same variable.
For example:
>>> x = 3
>>> x
3

>>> x += 15
>>> x
18

>>> x -= 2
>>> x
16

>>> x *= 2
>>> x
32

>>> x %= 5
>>> x
2

>>> x /= 1
>>> x
2.0

>>> x //= 2
>>> x
1.0

>>> x **= 5
>>> x
1.0
💡 Tips: these operators perform bitwise operations before assigning the result to the variable: &=, |=, ^=, >>=, <<=.
Membership Operators
You can check if an element is in a sequence or not with the operators: in and not in. The result will be either True or False.
For example:
>>> 5 in [1, 2, 3, 4, 5]
True

>>> 8 in [1, 2, 3, 4, 5]
False

>>> 5 in (1, 2, 3, 4, 5)
True

>>> 8 in (1, 2, 3, 4, 5)
False

>>> "a" in {"a": 1, "b": 2}
True

>>> "c" in {"a": 1, "b": 2}
False

>>> "h" in "Hello"
False

>>> "H" in "Hello"
True

>>> 5 not in [1, 2, 3, 4, 5]
False

>>> 8 not in (1, 2, 3, 4, 5)
True

>>> "a" not in {"a": 1, "b": 2}
False

>>> "c" not in {"a": 1, "b": 2}
True

>>> "h" not in "Hello"
True

>>> "H" not in "Hello"
False
We typically use them with variables that store sequences, like in this example:
>>> message = "Hello, World!"

>>> "e" in message
True