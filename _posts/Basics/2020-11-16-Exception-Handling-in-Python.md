---
layout: page
#
# Content
#
subheadline: "Exception Handling in Python"
title: "Exception Handling in Python"
teaser: "An error or unexpected event that that occurs while a program is running is called an exception. Thanks to the elements that we will see in just a moment, we can avoid terminating the program abruptly when this occurs."
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

Let's see the types of exceptions in Python and how we can handle them.
Common Exceptions in Python
This is a list of common exceptions in Python and why they occur:
ZeroDivisionError: raised when the second argument of a division or modulo operation is zero.

{% highlight python %}
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
{% endhighlight %}

IndexError: raised when we try to use an invalid index to access an element of a sequence.

{% highlight python %}
>>> my_list = [3, 4, 5, 6]

>>> my_list[15]
Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    my_list[15]
IndexError: list index out of range
{% endhighlight %}

KeyError: raised when we try to access a key-value pair that doesn't exist because the key is not in the dictionary.

{% highlight python %}
>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> my_dict["d"]
Traceback (most recent call last):
  File "<pyshell#6>", line 1, in <module>
    my_dict["d"]
KeyError: 'd'
{% endhighlight %}

NameError: raised when we use a variable that has not been defined previously.

{% highlight python %}
>>> b
Traceback (most recent call last):
  File "<pyshell#8>", line 1, in <module>
    b
NameError: name 'b' is not defined

{% endhighlight %}

RecursionError: raised when the interpreter detects that the maximum recursion depth is exceeded. This usually occurs when the process never reaches the base case. 
In the example below, we will get a 
{% highlight python %}
RecursionError
{% endhighlight %}
. The 
{% highlight python %}
factorial
{% endhighlight %}
 function is implemented recursively but the argument passed to the recursive call is 
{% highlight python %}
n
{% endhighlight %}
 instead of 
{% highlight python %}
n-1
{% endhighlight %}
. Unless the value is already 
{% highlight python %}
0
{% endhighlight %}
 or 
{% highlight python %}
1
{% endhighlight %}
, the base case will not be reached because the argument is not being decremented, so the process will continue and we will get this error.

{% highlight python %}
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
{% endhighlight %}


{% highlight python %}
try
{% endhighlight %}
 / 
{% highlight python %}
except
{% endhighlight %}
 in Python
We can use try/except in Python to catch the exceptions when they occur and handle them appropriately. This way, the problem can terminate appropriately or even recover from the exception. 
This is the basic syntax:

{% highlight python %}
try:
    <code_that_may_raise_an_exception>
except:
    <code_to_handle_the_exception_if_it_occurs>

{% endhighlight %}

For example, if we take user input to access an element in a list, the input might not be a valid index, so an exception could be raised:

{% highlight python %}
index = int(input("Enter the index: "))

try:
    my_list = [1, 2, 3, 4]
    print(my_list[index])
except:
    print("Please enter a valid index.")
{% endhighlight %}

If we enter an invalid value like 15, the output will be:

{% highlight python %}
Please enter a valid index.
{% endhighlight %}

Because the 
{% highlight python %}
except
{% endhighlight %}
 clause runs. However, if the value is valid, the code in 
{% highlight python %}
try
{% endhighlight %}
 will run as expected. 
Here we have another example:

{% highlight python %}
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except:
    print("Please enter valid values.")
{% endhighlight %}

The output is:

{% highlight python %}
Enter a: 5
Enter b: 0

Please enter valid values.
{% endhighlight %}

How to Catch a Specific Type of Exception in Python
Instead of catching and handling all possible exceptions that could occur in the 
{% highlight python %}
try
{% endhighlight %}
 clause, we could catch and handle a specific type of exception. We just need to specify the type of the exception after the 
{% highlight python %}
except
{% endhighlight %}
 keyword:

{% highlight python %}
try:
    <code_that_may_raise_an_exception>
except <exception_type>:
    <code_to_handle_an_exception_if_it_occurs>

{% endhighlight %}

For example:

{% highlight python %}
index = int(input("Enter the index: "))

try:
    my_list = [1, 2, 3, 4]
    print(my_list[index])
except IndexError: # specify the type
    print("Please enter a valid index.")
{% endhighlight %}


{% highlight python %}
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except ZeroDivisionError: # specify the type
    print("Please enter valid values.")
{% endhighlight %}

How to Assign a Name to the Exception Object in Python
We can specify a name for the exception object by assigning it to a variable that we can use in the 
{% highlight python %}
except
{% endhighlight %}
 clause. This will let us access its description and attributes. 
We only need to add 
{% highlight python %}
as <name>
{% endhighlight %}
, like this:

{% highlight python %}
try:
    <code_that_may_raise_an_exception>
except <exception_type> as <name>:
    <code_to_handle_an_exception_if_it_occurs>

{% endhighlight %}

For example:

{% highlight python %}
index = int(input("Enter the index: "))

try:
    my_list = [1, 2, 3, 4]
    print(my_list[index])
except IndexError as e:
    print("Exception raised:", e)
{% endhighlight %}

This is the output if we enter 
{% highlight python %}
15
{% endhighlight %}
 as the index:

{% highlight python %}
Enter the index: 15
Exception raised: list index out of range
{% endhighlight %}

This is another example:

{% highlight python %}
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except ZeroDivisionError as err:
    print("Please enter valid values.", err)

{% endhighlight %}

This is the output if we enter the value 
{% highlight python %}
0
{% endhighlight %}
 for 
{% highlight python %}
b
{% endhighlight %}
:

{% highlight python %}
Please enter valid values. division by zero
{% endhighlight %}


{% highlight python %}
try
{% endhighlight %}
 / 
{% highlight python %}
except
{% endhighlight %}
 / 
{% highlight python %}
else
{% endhighlight %}
 in Python
We can add an 
{% highlight python %}
else
{% endhighlight %}
 clause to this structure after 
{% highlight python %}
except
{% endhighlight %}
 if we want to choose what happens when no exceptions occur during the execution of the 
{% highlight python %}
try
{% endhighlight %}
 clause:

{% highlight python %}
try:
    <code_that_may_raise_an_exception>
except:
    <code_to_handle_an_exception_if_it_occurs>
else:
    <code_that_only_runs_if_no_exception_in_try>

{% endhighlight %}

For example:

{% highlight python %}
a = int(input("Enter a: "))
b = int(input("Enter b: "))

try:
    division = a / b
    print(division)
except ZeroDivisionError as err:
    print("Please enter valid values.", err)
else:
    print("Both values were valid.")
{% endhighlight %}

If we enter the values 
{% highlight python %}
5
{% endhighlight %}
 and 
{% highlight python %}
0
{% endhighlight %}
 for 
{% highlight python %}
a
{% endhighlight %}
 and 
{% highlight python %}
b
{% endhighlight %}
 respectively, the output is:

{% highlight python %}
Please enter valid values. division by zero
{% endhighlight %}

But if both values are valid, for example 
{% highlight python %}
5
{% endhighlight %}
 and 
{% highlight python %}
4
{% endhighlight %}
 for 
{% highlight python %}
a
{% endhighlight %}
 and 
{% highlight python %}
b
{% endhighlight %}
 respectively, the 
{% highlight python %}
else
{% endhighlight %}
 clause runs after 
{% highlight python %}
try
{% endhighlight %}
 is completed and we see:

{% highlight python %}
1.25
Both values were valid.
{% endhighlight %}


{% highlight python %}
try
{% endhighlight %}
 / 
{% highlight python %}
except
{% endhighlight %}
 / 
{% highlight python %}
else
{% endhighlight %}
 / 
{% highlight python %}
finally
{% endhighlight %}
 in Python
We can also add a 
{% highlight python %}
finally
{% endhighlight %}
 clause if we need to run code that should always run, even if an exception is raised in 
{% highlight python %}
try
{% endhighlight %}
.
For example:

{% highlight python %}
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
{% endhighlight %}

If both values are valid, the output is the result of the division and:

{% highlight python %}
Both values were valid.
Finally!
{% endhighlight %}

And if an exception is raised because 
{% highlight python %}
b
{% endhighlight %}
 is 
{% highlight python %}
0
{% endhighlight %}
, we see:

{% highlight python %}
Please enter valid values. division by zero
Finally!
{% endhighlight %}

The 
{% highlight python %}
finally
{% endhighlight %}
 clause always runs.
