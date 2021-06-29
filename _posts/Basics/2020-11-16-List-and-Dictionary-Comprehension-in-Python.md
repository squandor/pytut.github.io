---
layout: page
#
# Content
#
subheadline: "List and Dictionary Comprehension in Python"
title: "List and Dictionary Comprehension in Python"
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
A really nice feature of Python that you should know about is list and dictionary comprehension. This is just a way to create lists and dictionaries more compactly.
List Comprehension in Python
The syntax used to define list comprehensions usually follows one of these four patterns:
[<value_to_include> for <var> in <sequence>]
[<value_to_include> for <var1> in <sequence1> for <var2> in <sequence2>]
[<value_to_include> for <var> in <sequence> if <condition>]
[<value> for <var1> in <sequence1> for <var2> in <sequence2> if <condition>]
Here we have some examples:
>>> [i for i in range(4, 15)]
[4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]

>>> [chr(i) for i in range(67, 80)]
['C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O']

>>> [i**3 for i in range(2, 5)]
[8, 27, 64]

>>> [i + j for i in range(5, 8) for j in range(3, 6)]
[8, 9, 10, 9, 10, 11, 10, 11, 12]

>>> [k for k in range(3, 35) if k % 2 == 0]
[4, 6, 8, 10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34]

>>> [i * j for i in range(2, 6) for j in range(3, 7) if i % j == 0]
[9, 16, 25]
List Comprehensions vs. Generator Expressions in Python
List comprehensions are defined with square brackets []. This is different from generator expressions, which are defined with parentheses (). They look similar but they are quite different. Let's see why.
List comprehensions generate the entire sequence at once and store it in memory.Generator expressions yield the elements one at a time when they are requested.
We can check this with the sys module. In the example below, you can see that their size in memory is very different:
>>> import sys
>>> sys.getsizeof([i for i in range(500)])
2132
>>> sys.getsizeof((i for i in range(500)))
56
We can use generator expressions to iterate in a for loop and get the elements one at a time. But if we need to store the elements in a list, then we should use list comprehension. 
Dictionary Comprehension in Python
Now let's dive into dictionary comprehension. The basic syntax that we need to use to define a dictionary comprehension is:
{<key_value>: <value> for <var> in <sequence>}
{<key_value>: <value> for <var> in <sequence> if <condition>}
Here we have some examples of dictionary comprehension:
>>> {num: num**3 for num in range(3, 15)}
{3: 27, 4: 64, 5: 125, 6: 216, 7: 343, 8: 512, 9: 729, 10: 1000, 11: 1331, 12: 1728, 13: 2197, 14: 2744}

>>> {x: x + y for x in range(4, 8) for y in range(3, 7)}
{4: 10, 5: 11, 6: 12, 7: 13}
This is an example with a conditional where we take an existing dictionary and create a new dictionary with only the students who earned a passing grade greater than or equal to 60:
>>> grades = {"Nora": 78, "Gino": 100, "Talina": 56, "Elizabeth": 45, "Lulu": 67}

>>> approved_students = {student: grade for (student, grade) in grades.items() if grade >= 60}

>>> approved_students
{'Nora': 78, 'Gino': 100, 'Lulu': 67}
I really hope you liked this article and found it helpful. Now you know how to write and work with the most important elements of Python.
⭐ Subscribe to my YouTube channel and follow me on Twitter to find more coding tutorials and tips. Check out my online course Python Exercises for Beginners: Solve 100+ Coding Challenges

