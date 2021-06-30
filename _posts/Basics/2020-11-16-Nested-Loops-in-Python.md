---
layout: page
#
# Content
#
subheadline: "Nested Loops in Python"
title: "Nested Loops in Python"
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
We can write for loops within for loops and while loops within while loops. These inner loops are called nested loops. 
Nested For Loops in Python
{% highlight python %}>>> for i in range(3):
	for j in range(2):
		print(i, j)

		
0 0
0 1
1 0
1 1
2 0
2 1{% endhighlight %}
If we add print statements, we can see what is happening behind the scenes:
{% highlight python %}>>> for i in range(3):
	print("===> Outer Loop")
	print(f"i = {i}")
	for j in range(2):
		print("Inner Loop")
		print(f"j = {j}")

		
===> Outer Loop
i = 0
Inner Loop
j = 0
Inner Loop
j = 1
===> Outer Loop
i = 1
Inner Loop
j = 0
Inner Loop
j = 1
===> Outer Loop
i = 2
Inner Loop
j = 0
Inner Loop
j = 1{% endhighlight %}
The inner loop completes two iterations per iteration of the outer loop. The loop variables are updated when a new iteration starts.
This is another example:
{% highlight python %}>>> num_rows = 5

>>> for i in range(5):
	for num_cols in range(num_rows-i):
		print("*", end="")
	print()

	
*****
****
***
**
*{% endhighlight %}
Nested While Loops in Python
Here we have an example of nested while loops. In this case, we have to update the variables that are part of each condition to guarantee that the loops will stop.
{% highlight python %}>>> i = 5

>>> while i > 0:
	j = 0
	while j < 2:
		print(i, j)
		j += 1
	i -= 1

	
5 0
5 1
4 0
4 1
3 0
3 1
2 0
2 1
1 0
1 1{% endhighlight %}