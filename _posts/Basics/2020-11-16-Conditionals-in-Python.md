---
layout: page
#
# Content
#
subheadline: "Conditionals in Python"
title: "Conditionals in Python"
teaser: "Now let's see how we can write conditionals to make certain parts of our code run (or not) based on whether a condition is 
{% highlight python %}
True
{% endhighlight %}
 or 
{% highlight python %}
False
{% endhighlight %}
."
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

Now let's see how we can write conditionals to make certain parts of our code run (or not) based on whether a condition is 
{% highlight python %}
True
{% endhighlight %}
 or 
{% highlight python %}
False
{% endhighlight %}
.

{% highlight python %}
if
{% endhighlight %}
 statements in Python
This is the syntax of a basic 
{% highlight python %}
if
{% endhighlight %}
 statement:

{% highlight python %}
if <condition>:
    youre code
{% endhighlight %}

If the condition is 
{% highlight python %}
True
{% endhighlight %}
, the code will run. Else, if it's 
{% highlight python %}
False
{% endhighlight %}
, the code will not run.
Here we have some examples:
False Condition

{% highlight python %}
x = 5

if x > 9:
    print("Hello, World!")
{% endhighlight %}

The condition is 
{% highlight python %}
x > 9
{% endhighlight %}
 and the code is 
{% highlight python %}
print("Hello, World!")
{% endhighlight %}
. 
In this case, the condition is 
{% highlight python %}
False
{% endhighlight %}
, so there is no output.
True Condition
Here we have another example. Now the condition is 
{% highlight python %}
True
{% endhighlight %}
:

{% highlight python %}
color = "Blue"

if color == "Blue":
    print("This is my favorite color")
{% endhighlight %}

The output is:

{% highlight python %}
"This is my favorite color"
{% endhighlight %}

Code After the Conditional
Here we have an example with code that runs after the conditional has been completed. Notice that the last line is not indented, which means that it doesn't belong to the conditional.

{% highlight python %}
x = 5

if x > 9:
    print("Hello!")

print("End")
{% endhighlight %}

In this example, the condition 
{% highlight python %}
x > 9
{% endhighlight %}
 is 
{% highlight python %}
False
{% endhighlight %}
, so the first print statement doesn't run but the last print statement runs because it is not part of the conditional, so the output is:

{% highlight python %}
End
{% endhighlight %}

However, if the condition is 
{% highlight python %}
True
{% endhighlight %}
, like in this example:

{% highlight python %}
x = 15

if x > 9:
    print("Hello!")

print("End")
{% endhighlight %}

The output will be:

{% highlight python %}
Hello!
End
{% endhighlight %}

Examples of Conditionals
This is another example of a conditional:

{% highlight python %}
favorite_season = "Summer"

if favorite_season == "Summer":
    print("That is my favorite season too!")
{% endhighlight %}

In this case, the output will be:

{% highlight python %}
That is my favorite season too!
{% endhighlight %}

But if we change the value of 
{% highlight python %}
favorite_season
{% endhighlight %}
:

{% highlight python %}
favorite_season = "Winter"

if favorite_season == "Summer":
    print("That is my favorite season too!")
{% endhighlight %}

There will be no output because the condition will be 
{% highlight python %}
False
{% endhighlight %}
.

{% highlight python %}
if/else
{% endhighlight %}
 statements in Python
We can add an 
{% highlight python %}
else
{% endhighlight %}
 clause to the conditional if we need to specify what should happen when the condition is 
{% highlight python %}
False
{% endhighlight %}
.
This is the general syntax:

{% highlight python %}
if <condition>:
    youre code
else:
    youre code
{% endhighlight %}

Let's see an example with the 
{% highlight python %}
else
{% endhighlight %}
 clause:
True Condition

{% highlight python %}
x = 15

if x > 9:
    print("Hello!")
else:
    print("Bye!")

print("End")
{% endhighlight %}

The output is:

{% highlight python %}
Hello!
End
{% endhighlight %}

When the condition of the 
{% highlight python %}
if
{% endhighlight %}
 clause is 
{% highlight python %}
True
{% endhighlight %}
, this clause runs. The 
{% highlight python %}
else
{% endhighlight %}
 clause doesn't run.
False Condition
Now the 
{% highlight python %}
else
{% endhighlight %}
 clause runs because the condition is 
{% highlight python %}
False
{% endhighlight %}
.

{% highlight python %}
x = 5

if x > 9:
    print("Hello!")
else:
    print("Bye!")

print("End")
{% endhighlight %}

Now the output is:

{% highlight python %}
Bye!
End
{% endhighlight %}


{% highlight python %}
if/elif/else
{% endhighlight %}
 statements in Python
To customize our conditionals even further, we can add one or more 
{% highlight python %}
elif
{% endhighlight %}
 clauses to check and handle multiple conditions. Only the code of the first condition that evaluates to 
{% highlight python %}
True
{% endhighlight %}
 will run. 
First Condition True

{% highlight python %}
x = 5

if x < 9:
    print("Hello!")
elif x < 15:
    print("It's great to see you")
else:
    print("Bye!")

print("End")
{% endhighlight %}

We have two conditions 
{% highlight python %}
x < 9
{% endhighlight %}
 and 
{% highlight python %}
x < 15
{% endhighlight %}
. Only the code block from the first condition that is 
{% highlight python %}
True
{% endhighlight %}
 from top to bottom will be executed.
In this case, the output is:

{% highlight python %}
Hello!
End
{% endhighlight %}

Because the first condition is 
{% highlight python %}
True
{% endhighlight %}
: 
{% highlight python %}
x < 9
{% endhighlight %}
.
Second Condition True
If the first condition is 
{% highlight python %}
False
{% endhighlight %}
, then the second condition will be checked. 
In this example, the first condition 
{% highlight python %}
x < 9
{% endhighlight %}
 is 
{% highlight python %}
False
{% endhighlight %}
 but the second condition 
{% highlight python %}
x < 15
{% endhighlight %}
 is 
{% highlight python %}
True
{% endhighlight %}
, so the code that belongs to this clause will run.

{% highlight python %}
x = 13

if x < 9:
    print("Hello!")
elif x < 15:
    print("It's great to see you")
else:
    print("Bye!")

print("End")
{% endhighlight %}

The output is:

{% highlight python %}
It's great to see you
End
{% endhighlight %}

All Conditions are False
If all conditions all 
{% highlight python %}
False
{% endhighlight %}
, then the 
{% highlight python %}
else
{% endhighlight %}
 clause will run:

{% highlight python %}
x = 25

if x < 9:
    print("Hello!")
elif x < 15:
    print("It's great to see you")
else:
    print("Bye!")

print("End")
{% endhighlight %}

The output will be:

{% highlight python %}
Bye!
End
{% endhighlight %}

Multiple elif Clauses
We can add as many 
{% highlight python %}
elif
{% endhighlight %}
 clauses as needed. This is an example of a conditional with two 
{% highlight python %}
elif
{% endhighlight %}
 clauses:

{% highlight python %}
if favorite_season == "Winter":
    print("That is my favorite season too")
elif favorite_season == "Summer":
    print("Summer is amazing")
elif favorite_season == "Spring":
    print("I love spring")
else:
    print("Fall is my mom's favorite season")
{% endhighlight %}

Each condition will be checked and only the code block of the first condition that evaluates to 
{% highlight python %}
True
{% endhighlight %}
 will run. If none of them are 
{% highlight python %}
True
{% endhighlight %}
, the 
{% highlight python %}
else
{% endhighlight %}
 clause will run.
