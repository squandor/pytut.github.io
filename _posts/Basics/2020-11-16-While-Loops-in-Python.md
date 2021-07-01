---
layout: page
#
# Content
#
subheadline: "While Loops in Python"
title: "While Loops in Python"
teaser: "While loops are similar to for loops in that they let us repeat a block of code. The difference is that while loops run while a condition is 
{% highlight python %}
True
{% endhighlight %}
. "
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

While loops are similar to for loops in that they let us repeat a block of code. The difference is that while loops run while a condition is 
{% highlight python %}
True
{% endhighlight %}
. 
In a while loop, we define the condition, not the number of iterations. The loop stops when the condition is 
{% highlight python %}
False
{% endhighlight %}
.
This is the general syntax of a while loop:

{% highlight python %}
while <condition>:
    youre code
{% endhighlight %}

For example:

{% highlight python %}
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
{% endhighlight %}


{% highlight python %}
>>> x = 4

>>> while x >= 0:
	print("Hello" * x)
	x -= 1

	
HelloHelloHelloHello
HelloHelloHello
HelloHello
Hello
{% endhighlight %}


{% highlight python %}
>>> num = 5

>>> while num >= 1:
	print("*" * num)
	num -= 2

	
*****
***
*
{% endhighlight %}

Break and Continue
We can also use 
{% highlight python %}
break
{% endhighlight %}
 and 
{% highlight python %}
continue
{% endhighlight %}
 with while loops and they both work exactly the same:

{% highlight python %}
break
{% endhighlight %}
 stops the while loop immediately.
{% highlight python %}
continue
{% endhighlight %}
 stops the current iteration and starts the next one.
For example:

{% highlight python %}
>>> x = 5

>>> while x < 15:
	if x % 2 == 0:
		print("Even:", x)
		break
	print(x)
	x += 1
    

5
Even: 6
{% endhighlight %}


{% highlight python %}
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
{% endhighlight %}

The 
{% highlight python %}
else
{% endhighlight %}
 Clause
We can also add an 
{% highlight python %}
else
{% endhighlight %}
 clause to a while loop. If 
{% highlight python %}
break
{% endhighlight %}
 is found, the 
{% highlight python %}
else
{% endhighlight %}
 clause doesn't run but if the 
{% highlight python %}
break
{% endhighlight %}
 statement is not found, the 
{% highlight python %}
else
{% endhighlight %}
 clause runs.
In the example below, the 
{% highlight python %}
break
{% endhighlight %}
 statement is not found because none of the numbers are even before the condition becomes 
{% highlight python %}
False
{% endhighlight %}
, so the 
{% highlight python %}
else
{% endhighlight %}
 clause runs.

{% highlight python %}
x = 5

while x < 15:
	if x % 2 == 0:
		print("Even number found")
		break
	print(x)
	x += 2
else:
	print("All numbers were odd")
{% endhighlight %}

This is the output:

{% highlight python %}
5
7
9
11
13
All numbers were odd
{% endhighlight %}

But in this version of the example, the 
{% highlight python %}
break
{% endhighlight %}
 statement is found and the 
{% highlight python %}
else
{% endhighlight %}
 clause doesn't run:

{% highlight python %}
x = 5

while x < 15:
	if x % 2 == 0:
		print("Even number found")
		break
	print(x)
	x += 1 # Now we are incrementing the value by 1
else:
	print("All numbers were odd")
{% endhighlight %}

The output is:

{% highlight python %}
5
Even number found
{% endhighlight %}

Infinite While Loops
When we write and work with while loops, we can have something called an "infinite loop." If the condition is never 
{% highlight python %}
False
{% endhighlight %}
, the loop will never stop without external intervention. 
This usually happens when the variables in the condition are not updated properly during the execution of the loop.
For example:

{% highlight python %}
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
{% endhighlight %}

