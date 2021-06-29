---
layout: page
#
# Content
#
subheadline: "For Loops in Python"
title: "For Loops in Python"
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
Now you know how to write conditionals in Python, so let's start diving into loops. For loops are amazing programming structures that you can use to repeat a code block a specific number of times. 
This is the basic syntax to write a for loop in Python:
for <loop_variable> in <iterable>:
    {% highlight python %}
The iterable can be a list, tuple, dictionary, string, the sequence returned by range, a file, or any other type of iterable in Python. We will start with range().
The range() function in Python
This function returns a sequence of integers that we can use to determine how many iterations (repetitions) of the loop will be completed. The loop will complete one iteration per integer. 
This is the general syntax to write a for loop with range():
for <loop_variable> in range(<start>, <stop>, <step>):
    {% highlight python %}
As you can see, the range function has three parameters:
start: where the sequence of integers will start. By default, it's 0.stop: where the sequence of integers will stop (without including this value). step: the value that will be added to each element to get the next element in the sequence. By default, it's 1. 
You can pass 1, 2, or 3 arguments to range():
With 1 argument, the value is assigned to the stop parameter and the default values for the other two parameters are used. With 2 arguments, the values are assigned to the start and stop parameters and the default value for step is used.With 3 arguments, the values are assigned to the start, stop, and step parameters (in order).
Here we have some examples with one parameter:
for i in range(5):
    print(i)
Output:
0
1
2
3
4
>>> for j in range(15):
    print(j * 2)
Output:
0
2
4
6
8
10
12
14
16
18
20
22
24
26
28
In the example below, we repeat a string as many times as indicated by the value of the loop variable:
>>> for num in range(8):
	print("Hello" * num)
Output:
Hello
HelloHello
HelloHelloHello
HelloHelloHelloHello
HelloHelloHelloHelloHello
HelloHelloHelloHelloHelloHello
HelloHelloHelloHelloHelloHelloHello
We can also use for loops with built-in data structures such as lists:
>>> my_list = ["a", "b", "c", "d"]

>>> for i in range(len(my_list)):
	print(my_list[i])

Output:
a
b
c
d
These are some examples with two parameters:
>>> for i in range(2, 10):
	print(i)
Output:
2
3
4
5
6
7
8
9
Code:
>>> for j in range(2, 5):
	print("Python" * j)
Output:
PythonPython
PythonPythonPython
PythonPythonPythonPython
Code:
>>> my_list = ["a", "b", "c", "d"]

>>> for i in range(2, len(my_list)):
	print(my_list[i])
Output:
c
d
Code:
>>> my_list = ["a", "b", "c", "d"]

>>> for i in range(2, len(my_list)-1):
	my_list[i] *= i
Now the list is: ['a', 'b', 'cc', 'd']
These are some examples with three parameters:
>>> for i in range(3, 16, 2):
	print(i)
Output:
3
5
7
9
11
13
15
Code:
>>> for j in range(10, 5, -1):
	print(j)
Output:
10
9
8
7
6
Code:
>>> my_list = ["a", "b", "c", "d", "e", "f", "g"]

>>> for i in range(len(my_list)-1, 2, -1):
	print(my_list[i])
Output:
g
f
e
d
How to Iterate over Iterables in Python
We can iterate directly over iterables such as lists, tuples, dictionaries, strings, and files using for loops. We will get each one of their elements one at a time per iteration. This is very helpful to work with them directly.
Let's see some examples:
Iterate Over a String
If we iterate over a string, its characters will be assigned to the loop variable one by one (including spaces and symbols).
>>> message = "Hello, World!"

>>> for char in message:
	print(char)

	
H
e
l
l
o
,
 
W
o
r
l
d
!
We can also iterate over modified copies of the string by calling a string method where we specify the iterable in the for loop. This will assign the copy of the string as the iterable that will be used for the iterations, like this:
>>> word = "Hello"

>>> for char in word.lower(): # calling the string method
	print(char)

	
h
e
l
l
o
>>> word = "Hello"

>>> for char in word.upper(): # calling the string method
	print(char)

	
H
E
L
L
O
Iterate Over Lists and Tuples
>>> my_list = [2, 3, 4, 5]

>>> for num in my_list:
	print(num)
The output is:
2
3
4
5
Code:
>>> my_list = (2, 3, 4, 5)

>>> for num in my_list:
	if num % 2 == 0:
		print("Even")
	else:
		print("Odd")
Output:
Even
Odd
Even
Odd
Iterate Over the Keys, Values, and Key-Value Pairs of Dictionaries
We can iterate over the keys, values, and key-value pairs of a dictionary by calling specific dictionary methods. Let's see how.
To iterate over the keys, we write:
for <var> in <dictionary_variable>:
    {% highlight python %}
We just write the name of the variable that stores the dictionary as the iterable.
For example:
>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> for key in my_dict:
	print(key)

	
a
b
c
To iterate over the values, we use:
for <var> in <dictionary_variable>.values():
    {% highlight python %}
For example:
>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> for value in my_dict.values():
	print(value)

	
1
2
3
To iterate over the key-value pairs, we use:
for <key>, <value> in <dictionary_variable>.items():
    {% highlight python %}
>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> for key, value in my_dict.items():
	print(key, value)

	
a 1
b 2
c 3
If we define only one loop variable, this variable will contain a tuple with the key-value pair:
>>> my_dict = {"a": 1, "b": 2, "c": 3}
>>> for pair in my_dict.items():
	print(pair)

	
('a', 1)
('b', 2)
('c', 3)
Break and Continue in Python
Now you know how to iterate over sequences in Python. We also have loop control statements to customize what happens when the loop runs: break and continue.
The Break Statement
The break statement is used to stop the loop immediately. 
When a break statement is found, the loop stops and the program returns to its normal execution beyond the loop.
In the example below, we stop the loop when an even element is found. 
>>> my_list = [1, 2, 3, 4, 5]

>>> for elem in my_list:
	if elem % 2 == 0:
		print("Even:", elem)
		print("break")
		break
	else:
		print("Odd:", elem)

		
Odd: 1
Even: 2
break
The Continue Statement
The continue statement is used to skip the rest of the current iteration. 
When it is found during the execution of the loop, the current iteration stops and a new one begins with the updated value of the loop variable.
In the example below, we skip the current iteration if the element is even and we only print the value if the element is odd:
>>> my_list = [1, 2, 3, 4, 5]

>>> for elem in my_list:
	if elem % 2 == 0:
		print("continue")
		continue
	print("Odd:", elem)

	
Odd: 1
continue
Odd: 3
continue
Odd: 5
The zip() function in Python
zip() is an amazing built-in function that we can use in Python to iterate over multiple sequences at once, getting their corresponding elements in each iteration.
We just need to pass the sequences as arguments to the zip() function and use this result in the loop.
For example:
>>> my_list1 = [1, 2, 3, 4]
>>> my_list2 = [5, 6, 7, 8]

>>> for elem1, elem2 in zip(my_list1, my_list2):
	print(elem1, elem2)

	
1 5
2 6
3 7
4 8
The enumerate() Function in Python
You can also keep track of a counter while the loop runs with the enum() function. It is commonly used to iterate over a sequence and get the corresponding index.
For example:
>>> my_list = [5, 6, 7, 8]

>>> for i, elem in enumerate(my_list):
	print(i, elem)

	
0 5
1 6
2 7
3 8
>>> word = "Hello"

>>> for i, char in enumerate(word):
	print(i, char)

	
0 H
1 e
2 l
3 l
4 o
If you start the counter from 0, you can use the index and the current value in the same iteration to modify the sequence:
>>> my_list = [5, 6, 7, 8]

>>> for index, num in enumerate(my_list):
	my_list[index] = num * 3

>>> my_list
[15, 18, 21, 24]
You can start the counter from a different number by passing a second argument to enumerate():
>>> word = "Hello"

>>> for i, char in enumerate(word, 2):
	print(i, char)

	
2 H
3 e
4 l
5 l
6 o
The else Clause
For loops also have an else clause. You can add this clause to the loop if you want to run a specific block of code when the loop completes all its iterations without finding the break statement.
In the example below, we try to find an element greater than 6 in the list. That element is not found, so break doesn't run and the else clause runs.
my_list = [1, 2, 3, 4, 5]

for elem in my_list:
    if elem > 6:
        print("Found")
        break
else:
    print("Not Found")
The output is:
Not Found
However, if the break statement runs, the else clause doesn't run. We can see this in the example below:
my_list = [1, 2, 3, 4, 5, 8] # Now the list has the value 8

for elem in my_list:
    if elem > 6:
        print("Found")
        break
else:
    print("Not Found")
The output is:
Found