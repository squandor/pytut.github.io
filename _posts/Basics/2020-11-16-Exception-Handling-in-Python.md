---
layout: page
#
# Content
#
subheadline: "Exception Handling in Python"
title: "Exception Handling in Python"
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
An error or unexpected event that that occurs while a program is running is called an exception. Thanks to the elements that we will see in just a moment, we can avoid terminating the program abruptly when this occurs.
Let's see the types of exceptions in Python and how we can handle them.
Common Exceptions in Python
This is a list of common exceptions in Python and why they occur:
ZeroDivisionError: raised when the second argument of a division or modulo operation is zero.
>>> 5 / 0
Traceback (most recent call last):
  File "<pyshell#0>", line 1, in <module>
    5 / 0
ZeroDivisionError: division by zero

>>> 7 // 0
Traceback (most recent call last):
  File "<pyshell#1>", line 1, in <module>
    7 // 0
ZeroDivisionError: integer division or modulo by zero

>>> 8 % 0
Traceback (most recent call last):
  File "<pyshell#2>", line 1, in <module>
    8 % 0
ZeroDivisionError: integer division or modulo by zero
IndexError: raised when we try to use an invalid index to access an element of a sequence.
>>> my_list = [3, 4, 5, 6]

>>> my_list[15]
Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    my_list[15]
IndexError: list index out of range
KeyError: raised when we try to access a key-value pair that doesn't exist because the key is not in the dictionary.
>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> my_dict["d"]
Traceback (most recent call last):
  File "<pyshell#6>", line 1, in <module>
    my_dict["d"]
KeyError: 'd'
NameError: raised when we use a variable that has not been defined previously.
>>> b
Traceback (most recent call last):
  File "<pyshell#8>", line 1, in <module>
    b
NameError: name 'b' is not defined

RecursionError: raised when the interpreter detects that the maximum recursion depth is exceeded. This usually occurs when the process never reaches the base case. 
In the example below, we will get a RecursionError. The factorial function is implemented recursively but the argument passed to the recursive call is n instead of n-1. Unless the value is already 0 or 1, the base case will not be reached because the argument is not being decremented, so the process will continue and we will get this error.
>>> def factorial(n):
	if n == 0 or n == 1:
		return 1
	else:
		return n * factorial(n)

	
>>> factorial(5)
Traceback (most recent call last):
  File "<pyshell#6>", line 1, in <module>
    factorial(5)
  File "<pyshell#5>", line 5, in factorial
    return n * factorial(n)
  File "<pyshell#5>", line 5, in factorial
    return n * factorial(n)
  File "<pyshell#5>", line 5, in factorial
    return n * factorial(n)
  [Previous line repeated 1021 more times]
  File "<pyshell#5>", line 2, in factorial
    if n == 0 or n == 1:
RecursionError: maximum recursion depth exceeded in comparison
try / except in Python
We can use try/except in Python to catch the exceptions when they occur and handle them appropriately. This way, the problem can terminate appropriately or even recover from the exception. 
This is the basic syntax:
try:
    <code_that_may_raise_an_exception>
except:
    <code_to_handle_the_exception_if_it_occurs>

For example, if we take user input to access an element in a list, the input might not be a valid index, so an exception could be raised:
index = int(input("Enter the index: "))

try:
    my_list = [1, 2, 3, 4]
    print(my_list[index])
except:
    print("Please enter a valid index.")
If we enter an invalid value like 15, the output will be:
Please enter a valid index.
Because the except clause runs. However, if the value is valid, the code in try will run as expected. 
Here we have another example:
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except:
    print("Please enter valid values.")
The output is:
Enter a: 5
Enter b: 0

Please enter valid values.
How to Catch a Specific Type of Exception in Python
Instead of catching and handling all possible exceptions that could occur in the try clause, we could catch and handle a specific type of exception. We just need to specify the type of the exception after the except keyword:
try:
    <code_that_may_raise_an_exception>
except <exception_type>:
    <code_to_handle_an_exception_if_it_occurs>

For example:
index = int(input("Enter the index: "))

try:
    my_list = [1, 2, 3, 4]
    print(my_list[index])
except IndexError: # specify the type
    print("Please enter a valid index.")
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except ZeroDivisionError: # specify the type
    print("Please enter valid values.")
How to Assign a Name to the Exception Object in Python
We can specify a name for the exception object by assigning it to a variable that we can use in the except clause. This will let us access its description and attributes. 
We only need to add as <name>, like this:
try:
    <code_that_may_raise_an_exception>
except <exception_type> as <name>:
    <code_to_handle_an_exception_if_it_occurs>

For example:
index = int(input("Enter the index: "))

try:
    my_list = [1, 2, 3, 4]
    print(my_list[index])
except IndexError as e:
    print("Exception raised:", e)
This is the output if we enter 15 as the index:
Enter the index: 15
Exception raised: list index out of range
This is another example:
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except ZeroDivisionError as err:
    print("Please enter valid values.", err)

This is the output if we enter the value 0 for b:
Please enter valid values. division by zero
try / except / else in Python
We can add an else clause to this structure after except if we want to choose what happens when no exceptions occur during the execution of the try clause:
try:
    <code_that_may_raise_an_exception>
except:
    <code_to_handle_an_exception_if_it_occurs>
else:
    <code_that_only_runs_if_no_exception_in_try>

For example:
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except ZeroDivisionError as err:
    print("Please enter valid values.", err)
else:
    print("Both values were valid.")
If we enter the values 5 and 0 for a and b respectively, the output is:
Please enter valid values. division by zero
But if both values are valid, for example 5 and 4 for a and b respectively, the else clause runs after try is completed and we see:
1.25
Both values were valid.
try / except / else / finally in Python
We can also add a finally clause if we need to run code that should always run, even if an exception is raised in try.
For example:
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except ZeroDivisionError as err:
    print("Please enter valid values.", err)
else:
    print("Both values were valid.")
finally:
    print("Finally!")
If both values are valid, the output is the result of the division and:
Both values were valid.
Finally!
And if an exception is raised because b is 0, we see:
Please enter valid values. division by zero
Finally!
The finally clause always runs.