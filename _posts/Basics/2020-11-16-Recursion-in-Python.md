---
layout: page
#
# Content
#
subheadline: "Recursion in Python"
title: "Recursion in Python"
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
A recursive function is a function that calls itself. These functions have a base case that stops the recursive process and a recursive case that continues the recursive process by making another recursive call.
Here we have some examples in Python:
{% highlight python %}def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n-1){% endhighlight %}Recursive Factorial Function
{% highlight python %}def fibonacci(n):
    if n == 0 or n == 1:
        return n
    else:
        return fibonacci(n-1) + fibonacci(n-2){% endhighlight %}The Fibonacci Function
{% highlight python %}def find_power(a, b):
    if b == 0:
        return 1
    else:
        return a * find_power(a, b-1){% endhighlight %}Find a Power Recursively