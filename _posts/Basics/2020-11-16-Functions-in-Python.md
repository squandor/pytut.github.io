---
layout: page
#
# Content
#
subheadline: "Functions in Python"
title: "Functions in Python"
teaser: "In Python, we can define functions to make our code reusable, more readable, and organized. This is the basic syntax of a Python function:"
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


{% highlight python %}
def <function_name>(<param1>, <param2>, ...):
    youre code
{% endhighlight %}

Function with No Parameters in Python
A function with no parameters has an empty pair of parentheses after its name in the function definition. For example:

{% highlight python %}
def print_pattern():
    size = 4
    for i in range(size):
        print("*" * size)
{% endhighlight %}

This is the output when we call the function:

{% highlight python %}
>>> print_pattern()
****
****
****
****
{% endhighlight %}

Function with One Parameter in Python
A function with one or more parameters has a list of parameters surrounded by parentheses after its name in the function definition:

{% highlight python %}
def welcome_student(name):
    print(f"Hi, {name}! Welcome to class.")
{% endhighlight %}

When we call the function, we just need to pass one value as argument and that value will be replaced where we use the parameter in the function definition:

{% highlight python %}
>>> welcome_student("Nora")
Hi, Nora! Welcome to class.
{% endhighlight %}

Here we have another example – a function that prints a pattern made with asterisks. You have to specify how many rows you want to print:

{% highlight python %}
def print_pattern(num_rows):
    for i in range(num_rows):
        for num_cols in range(num_rows-i):
            print("*", end="")
        print()
{% endhighlight %}

You can see the different outputs for different values of 
{% highlight python %}
num_rows
{% endhighlight %}
:

{% highlight python %}
>>> print_pattern(3)
***
**
*

>>> print_pattern(5)
*****
****
***
**
*

>>> print_pattern(8)
********
*******
******
*****
****
***
**
*
{% endhighlight %}

Functions with Two or More Parameters in Python
To define two or more parameters, we just separate them with a comma:

{% highlight python %}
def print_sum(a, b):
    print(a + b)

{% endhighlight %}

Now when we call the function, we must pass two arguments:

{% highlight python %}
>>> print_sum(4, 5)
9

>>> print_sum(8, 9)
17

>>> print_sum(0, 0)
0

>>> print_sum(3, 5)
8
{% endhighlight %}

We can adapt the function that we just saw with one parameter to work with two parameters and print a pattern with a customized character:

{% highlight python %}
def print_pattern(num_rows, char):
	for i in range(num_rows):
		for num_cols in range(num_rows-i):
			print(char, end="")
		print()
{% endhighlight %}

You can see the output with the customized character is that we call the function passing the two arguments:

{% highlight python %}
>>> print_pattern(5, "A")
AAAAA
AAAA
AAA
AA
A

>>> print_pattern(8, "%")
%%%%%%%%
%%%%%%%
%%%%%%
%%%%%
%%%%
%%%
%%
%

>>> print_pattern(10, "#")
##########
#########
########
#######
######
#####
####
###
##
#
{% endhighlight %}

How to Return a Value in Python
Awesome. Now you know how to define a function, so let's see how you can work with return statements. 
We will often need to return a value from a function. We can do this with the 
{% highlight python %}
return
{% endhighlight %}
 statement in Python. We just need to write this in the function definition:

{% highlight python %}
return <value_to_return>
{% endhighlight %}

Here we have an example:

{% highlight python %}
def get_rectangle_area(length, width):
    return length * width
{% endhighlight %}

Now we can call the function and assign the result to a variable because the result is returned by the function:

{% highlight python %}
>>> area = get_rectangle_area(4, 5)
>>> area
20
{% endhighlight %}

We can also use 
{% highlight python %}
return
{% endhighlight %}
 with a conditional to return a value based on whether a condition is 
{% highlight python %}
True
{% endhighlight %}
 or 
{% highlight python %}
False
{% endhighlight %}
.
In this example, the function returns the first even element found in the sequence:

{% highlight python %}
def get_first_even(seq):
    for elem in seq:
        if elem % 2 == 0:
            return elem
        else:
            return None
{% endhighlight %}

If we call the function, we can see the expected results:

{% highlight python %}
>>> value1 = get_first_even([2, 3, 4, 5])
>>> value1
2
{% endhighlight %}


{% highlight python %}
>>> value2 = get_first_even([3, 5, 7, 9])
>>> print(value2)
None
{% endhighlight %}

The Style Guide for Python Code recommends using return statements consistently. It mentions that we should:
Be consistent in return statements. Either all return statements in a function should return an expression, or none of them should. If any return statement returns an expression, any return statements where no value is returned should explicitly state this as return None, and an explicit return statement should be present at the end of the function (if reachable)
Default Arguments in Python
We can assign default arguments for the parameters of our function. To do this, we just need to write 
{% highlight python %}
<parameter>=<value>
{% endhighlight %}
 in the list of parameters.
In this example, we assign the default value 5 to the parameter 
{% highlight python %}
b
{% endhighlight %}
. If we omit this value when we call the function, the default value will be used.

{% highlight python %}
def print_product(a, b=5):
    print(a * b)
{% endhighlight %}

If we call the function without this argument, you can see the output:

{% highlight python %}
>>> print_product(4)
20
{% endhighlight %}

We confirm that the default argument 5 was used in the operation. 
But we can also assign a custom value for 
{% highlight python %}
b
{% endhighlight %}
 by passing a second argument:

{% highlight python %}
>>> print_product(3, 4)
12
{% endhighlight %}

Here we have another example with the function that we wrote to print a pattern. We assign the default value 
{% highlight python %}
"*"
{% endhighlight %}
 to the 
{% highlight python %}
char
{% endhighlight %}
 parameter.

{% highlight python %}
def print_pattern(num_rows, char="*"):
	for i in range(num_rows):
		for num_cols in range(num_rows-i):
			print(char, end="")
		print()
{% endhighlight %}

Now we have the option to use the default value or customize it:

{% highlight python %}
>>> print_pattern(5)
*****
****
***
**
*

>>> print_pattern(6, "&")
&&&&&&
&&&&&
&&&&
&&&
&&
&
{% endhighlight %}

