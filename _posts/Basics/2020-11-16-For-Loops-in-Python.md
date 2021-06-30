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
{% highlight python %}for <loop_variable> in <iterable>:
    <code>{% endhighlight %}
The iterable can be a list, tuple, dictionary, string, the sequence returned by range, a file, or any other type of iterable in Python. We will start with {% highlight python %}range(){% endhighlight %}.
The {% highlight python %}range(){% endhighlight %} function in Python
This function returns a sequence of integers that we can use to determine how many iterations (repetitions) of the loop will be completed. The loop will complete one iteration per integer. 
This is the general syntax to write a for loop with {% highlight python %}range(){% endhighlight %}:
{% highlight python %}for <loop_variable> in range(<start>, <stop>, <step>):
    <code>{% endhighlight %}
As you can see, the range function has three parameters:
{% highlight python %}start{% endhighlight %}: where the sequence of integers will start. By default, it's {% highlight python %}0{% endhighlight %}.{% highlight python %}stop{% endhighlight %}: where the sequence of integers will stop (without including this value). {% highlight python %}step{% endhighlight %}: the value that will be added to each element to get the next element in the sequence. By default, it's {% highlight python %}1{% endhighlight %}. 
You can pass 1, 2, or 3 arguments to {% highlight python %}range(){% endhighlight %}:
With 1 argument, the value is assigned to the {% highlight python %}stop{% endhighlight %} parameter and the default values for the other two parameters are used. With 2 arguments, the values are assigned to the {% highlight python %}start{% endhighlight %} and {% highlight python %}stop{% endhighlight %} parameters and the default value for {% highlight python %}step{% endhighlight %} is used.With 3 arguments, the values are assigned to the {% highlight python %}start{% endhighlight %}, {% highlight python %}stop{% endhighlight %}, and {% highlight python %}step{% endhighlight %} parameters (in order).
Here we have some examples with one parameter:
{% highlight python %}for i in range(5):
    print(i){% endhighlight %}
Output:
{% highlight python %}0
1
2
3
4{% endhighlight %}
{% highlight python %}>>> for j in range(15):
    print(j * 2){% endhighlight %}
Output:
{% highlight python %}0
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
28{% endhighlight %}
In the example below, we repeat a string as many times as indicated by the value of the loop variable:
{% highlight python %}>>> for num in range(8):
	print("Hello" * num){% endhighlight %}
Output:
{% highlight python %}Hello
HelloHello
HelloHelloHello
HelloHelloHelloHello
HelloHelloHelloHelloHello
HelloHelloHelloHelloHelloHello
HelloHelloHelloHelloHelloHelloHello{% endhighlight %}
We can also use for loops with built-in data structures such as lists:
{% highlight python %}>>> my_list = ["a", "b", "c", "d"]

>>> for i in range(len(my_list)):
	print(my_list[i])
{% endhighlight %}
Output:
{% highlight python %}a
b
c
d{% endhighlight %}
These are some examples with two parameters:
{% highlight python %}>>> for i in range(2, 10):
	print(i){% endhighlight %}
Output:
{% highlight python %}2
3
4
5
6
7
8
9{% endhighlight %}
Code:
{% highlight python %}>>> for j in range(2, 5):
	print("Python" * j){% endhighlight %}
Output:
{% highlight python %}PythonPython
PythonPythonPython
PythonPythonPythonPython{% endhighlight %}
Code:
{% highlight python %}>>> my_list = ["a", "b", "c", "d"]

>>> for i in range(2, len(my_list)):
	print(my_list[i]){% endhighlight %}
Output:
{% highlight python %}c
d{% endhighlight %}
Code:
{% highlight python %}>>> my_list = ["a", "b", "c", "d"]

>>> for i in range(2, len(my_list)-1):
	my_list[i] *= i{% endhighlight %}
Now the list is: {% highlight python %}['a', 'b', 'cc', 'd']{% endhighlight %}
These are some examples with three parameters:
{% highlight python %}>>> for i in range(3, 16, 2):
	print(i){% endhighlight %}
Output:
{% highlight python %}3
5
7
9
11
13
15{% endhighlight %}
Code:
{% highlight python %}>>> for j in range(10, 5, -1):
	print(j){% endhighlight %}
Output:
{% highlight python %}10
9
8
7
6{% endhighlight %}
Code:
{% highlight python %}>>> my_list = ["a", "b", "c", "d", "e", "f", "g"]

>>> for i in range(len(my_list)-1, 2, -1):
	print(my_list[i]){% endhighlight %}
Output:
{% highlight python %}g
f
e
d{% endhighlight %}
How to Iterate over Iterables in Python
We can iterate directly over iterables such as lists, tuples, dictionaries, strings, and files using for loops. We will get each one of their elements one at a time per iteration. This is very helpful to work with them directly.
Let's see some examples:
Iterate Over a String
If we iterate over a string, its characters will be assigned to the loop variable one by one (including spaces and symbols).
{% highlight python %}>>> message = "Hello, World!"

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
!{% endhighlight %}
We can also iterate over modified copies of the string by calling a string method where we specify the iterable in the for loop. This will assign the copy of the string as the iterable that will be used for the iterations, like this:
{% highlight python %}>>> word = "Hello"

>>> for char in word.lower(): # calling the string method
	print(char)

	
h
e
l
l
o{% endhighlight %}
{% highlight python %}>>> word = "Hello"

>>> for char in word.upper(): # calling the string method
	print(char)

	
H
E
L
L
O{% endhighlight %}
Iterate Over Lists and Tuples
{% highlight python %}>>> my_list = [2, 3, 4, 5]

>>> for num in my_list:
	print(num){% endhighlight %}
The output is:
{% highlight python %}2
3
4
5{% endhighlight %}
Code:
{% highlight python %}>>> my_list = (2, 3, 4, 5)

>>> for num in my_list:
	if num % 2 == 0:
		print("Even")
	else:
		print("Odd"){% endhighlight %}
Output:
{% highlight python %}Even
Odd
Even
Odd{% endhighlight %}
Iterate Over the Keys, Values, and Key-Value Pairs of Dictionaries
We can iterate over the keys, values, and key-value pairs of a dictionary by calling specific dictionary methods. Let's see how.
To iterate over the keys, we write:
{% highlight python %}for <var> in <dictionary_variable>:
    <code>{% endhighlight %}
We just write the name of the variable that stores the dictionary as the iterable.
For example:
{% highlight python %}>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> for key in my_dict:
	print(key)

	
a
b
c{% endhighlight %}
To iterate over the values, we use:
{% highlight python %}for <var> in <dictionary_variable>.values():
    <code>{% endhighlight %}
For example:
{% highlight python %}>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> for value in my_dict.values():
	print(value)

	
1
2
3{% endhighlight %}
To iterate over the key-value pairs, we use:
{% highlight python %}for <key>, <value> in <dictionary_variable>.items():
    <code>{% endhighlight %}
{% highlight python %}>>> my_dict = {"a": 1, "b": 2, "c": 3}

>>> for key, value in my_dict.items():
	print(key, value)

	
a 1
b 2
c 3{% endhighlight %}
If we define only one loop variable, this variable will contain a tuple with the key-value pair:
{% highlight python %}>>> my_dict = {"a": 1, "b": 2, "c": 3}
>>> for pair in my_dict.items():
	print(pair)

	
('a', 1)
('b', 2)
('c', 3){% endhighlight %}
Break and Continue in Python
Now you know how to iterate over sequences in Python. We also have loop control statements to customize what happens when the loop runs: {% highlight python %}break{% endhighlight %} and {% highlight python %}continue{% endhighlight %}.
The Break Statement
The {% highlight python %}break{% endhighlight %} statement is used to stop the loop immediately. 
When a {% highlight python %}break{% endhighlight %} statement is found, the loop stops and the program returns to its normal execution beyond the loop.
In the example below, we stop the loop when an even element is found. 
{% highlight python %}>>> my_list = [1, 2, 3, 4, 5]

>>> for elem in my_list:
	if elem % 2 == 0:
		print("Even:", elem)
		print("break")
		break
	else:
		print("Odd:", elem)

		
Odd: 1
Even: 2
break{% endhighlight %}
The Continue Statement
The {% highlight python %}continue{% endhighlight %} statement is used to skip the rest of the current iteration. 
When it is found during the execution of the loop, the current iteration stops and a new one begins with the updated value of the loop variable.
In the example below, we skip the current iteration if the element is even and we only print the value if the element is odd:
{% highlight python %}>>> my_list = [1, 2, 3, 4, 5]

>>> for elem in my_list:
	if elem % 2 == 0:
		print("continue")
		continue
	print("Odd:", elem)

	
Odd: 1
continue
Odd: 3
continue
Odd: 5{% endhighlight %}
The zip() function in Python
{% highlight python %}zip(){% endhighlight %} is an amazing built-in function that we can use in Python to iterate over multiple sequences at once, getting their corresponding elements in each iteration.
We just need to pass the sequences as arguments to the {% highlight python %}zip(){% endhighlight %} function and use this result in the loop.
For example:
{% highlight python %}>>> my_list1 = [1, 2, 3, 4]
>>> my_list2 = [5, 6, 7, 8]

>>> for elem1, elem2 in zip(my_list1, my_list2):
	print(elem1, elem2)

	
1 5
2 6
3 7
4 8{% endhighlight %}
The enumerate() Function in Python
You can also keep track of a counter while the loop runs with the {% highlight python %}enum(){% endhighlight %} function. It is commonly used to iterate over a sequence and get the corresponding index.
For example:
{% highlight python %}>>> my_list = [5, 6, 7, 8]

>>> for i, elem in enumerate(my_list):
	print(i, elem)

	
0 5
1 6
2 7
3 8{% endhighlight %}
{% highlight python %}>>> word = "Hello"

>>> for i, char in enumerate(word):
	print(i, char)

	
0 H
1 e
2 l
3 l
4 o{% endhighlight %}
If you start the counter from {% highlight python %}0{% endhighlight %}, you can use the index and the current value in the same iteration to modify the sequence:
{% highlight python %}>>> my_list = [5, 6, 7, 8]

>>> for index, num in enumerate(my_list):
	my_list[index] = num * 3

>>> my_list
[15, 18, 21, 24]{% endhighlight %}
You can start the counter from a different number by passing a second argument to {% highlight python %}enumerate(){% endhighlight %}:
{% highlight python %}>>> word = "Hello"

>>> for i, char in enumerate(word, 2):
	print(i, char)

	
2 H
3 e
4 l
5 l
6 o{% endhighlight %}
The else Clause
For loops also have an {% highlight python %}else{% endhighlight %} clause. You can add this clause to the loop if you want to run a specific block of code when the loop completes all its iterations without finding the {% highlight python %}break{% endhighlight %} statement.
In the example below, we try to find an element greater than 6 in the list. That element is not found, so {% highlight python %}break{% endhighlight %} doesn't run and the {% highlight python %}else{% endhighlight %} clause runs.
{% highlight python %}my_list = [1, 2, 3, 4, 5]

for elem in my_list:
    if elem > 6:
        print("Found")
        break
else:
    print("Not Found"){% endhighlight %}
The output is:
{% highlight python %}Not Found{% endhighlight %}
However, if the {% highlight python %}break{% endhighlight %} statement runs, the {% highlight python %}else{% endhighlight %} clause doesn't run. We can see this in the example below:
{% highlight python %}my_list = [1, 2, 3, 4, 5, 8] # Now the list has the value 8

for elem in my_list:
    if elem > 6:
        print("Found")
        break
else:
    print("Not Found"){% endhighlight %}
The output is:
{% highlight python %}Found{% endhighlight %}
