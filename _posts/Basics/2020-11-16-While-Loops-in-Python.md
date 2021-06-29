---
layout: page
#
# Content
#
subheadline: "While Loops in Python"
title: "While Loops in Python"
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
While loops are similar to for loops in that they let us repeat a block of code. The difference is that while loops run while a condition is True. 
In a while loop, we define the condition, not the number of iterations. The loop stops when the condition is False.
This is the general syntax of a while loop:
while <condition>:
    {% highlight python %}
For example:
>>> x = 6

>>> while x < 15:
	print(x)
	x += 1

	
6
7
8
9
10
11
12
13
14
>>> x = 4

>>> while x >= 0:
	print("Hello" * x)
	x -= 1

	
HelloHelloHelloHello
HelloHelloHello
HelloHello
Hello
>>> num = 5

>>> while num >= 1:
	print("*" * num)
	num -= 2

	
*****
***
*
Break and Continue
We can also use break and continue with while loops and they both work exactly the same:
break stops the while loop immediately.continue stops the current iteration and starts the next one.
For example:
>>> x = 5

>>> while x < 15:
	if x % 2 == 0:
		print("Even:", x)
		break
	print(x)
	x += 1
    

5
Even: 6
>>> x = 5

>>> while x < 15:
	if x % 2 == 0:
		x += 1
		continue
	print("Odd:", x)
	x += 1

	
Odd: 5
Odd: 7
Odd: 9
Odd: 11
Odd: 13
The else Clause
We can also add an else clause to a while loop. If break is found, the else clause doesn't run but if the break statement is not found, the else clause runs.
In the example below, the break statement is not found because none of the numbers are even before the condition becomes False, so the else clause runs.
x = 5

while x < 15:
	if x % 2 == 0:
		print("Even number found")
		break
	print(x)
	x += 2
else:
	print("All numbers were odd")
This is the output:
5
7
9
11
13
All numbers were odd
But in this version of the example, the break statement is found and the else clause doesn't run:
x = 5

while x < 15:
	if x % 2 == 0:
		print("Even number found")
		break
	print(x)
	x += 1 # Now we are incrementing the value by 1
else:
	print("All numbers were odd")
The output is:
5
Even number found
Infinite While Loops
When we write and work with while loops, we can have something called an "infinite loop." If the condition is never False, the loop will never stop without external intervention. 
This usually happens when the variables in the condition are not updated properly during the execution of the loop.
For example:
>>> x = 5

>>> while x > 2:
	print(x)

	
5
5
5
5
5
5
5
5
5
.
.
.
# The output continues indefinitely