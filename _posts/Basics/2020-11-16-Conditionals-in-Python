---
layout: page
#
# Content
#
subheadline: "Conditionals in Python"
title: "Conditionals in Python"
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
Now let's see how we can write conditionals to make certain parts of our code run (or not) based on whether a condition is True or False.
if statements in Python
This is the syntax of a basic if statement:
if <condition>:
    {% highlight python %}
If the condition is True, the code will run. Else, if it's False, the code will not run.
Here we have some examples:
False Condition
x = 5

if x > 9:
    print("Hello, World!")
The condition is x > 9 and the code is print("Hello, World!"). 
In this case, the condition is False, so there is no output.
True Condition
Here we have another example. Now the condition is True:
color = "Blue"

if color == "Blue":
    print("This is my favorite color")
The output is:
"This is my favorite color"
Code After the Conditional
Here we have an example with code that runs after the conditional has been completed. Notice that the last line is not indented, which means that it doesn't belong to the conditional.
x = 5

if x > 9:
    print("Hello!")

print("End")
In this example, the condition x > 9 is False, so the first print statement doesn't run but the last print statement runs because it is not part of the conditional, so the output is:
End
However, if the condition is True, like in this example:
x = 15

if x > 9:
    print("Hello!")

print("End")
The output will be:
Hello!
End
Examples of Conditionals
This is another example of a conditional:
favorite_season = "Summer"

if favorite_season == "Summer":
    print("That is my favorite season too!")
In this case, the output will be:
That is my favorite season too!
But if we change the value of favorite_season:
favorite_season = "Winter"

if favorite_season == "Summer":
    print("That is my favorite season too!")
There will be no output because the condition will be False.
if/else statements in Python
We can add an else clause to the conditional if we need to specify what should happen when the condition is False.
This is the general syntax:
if <condition>:
    {% highlight python %}
else:
    {% highlight python %}
Let's see an example with the else clause:
True Condition
x = 15

if x > 9:
    print("Hello!")
else:
    print("Bye!")

print("End")
The output is:
Hello!
End
When the condition of the if clause is True, this clause runs. The else clause doesn't run.
False Condition
Now the else clause runs because the condition is False.
x = 5

if x > 9:
    print("Hello!")
else:
    print("Bye!")

print("End")
Now the output is:
Bye!
End
if/elif/else statements in Python
To customize our conditionals even further, we can add one or more elif clauses to check and handle multiple conditions. Only the code of the first condition that evaluates to True will run. 
First Condition True
x = 5

if x < 9:
    print("Hello!")
elif x < 15:
    print("It's great to see you")
else:
    print("Bye!")

print("End")
We have two conditions x < 9 and x < 15. Only the code block from the first condition that is True from top to bottom will be executed.
In this case, the output is:
Hello!
End
Because the first condition is True: x < 9.
Second Condition True
If the first condition is False, then the second condition will be checked. 
In this example, the first condition x < 9 is False but the second condition x < 15 is True, so the code that belongs to this clause will run.
x = 13

if x < 9:
    print("Hello!")
elif x < 15:
    print("It's great to see you")
else:
    print("Bye!")

print("End")
The output is:
It's great to see you
End
All Conditions are False
If all conditions all False, then the else clause will run:
x = 25

if x < 9:
    print("Hello!")
elif x < 15:
    print("It's great to see you")
else:
    print("Bye!")

print("End")
The output will be:
Bye!
End
Multiple elif Clauses
We can add as many elif clauses as needed. This is an example of a conditional with two elif clauses:
if favorite_season == "Winter":
    print("That is my favorite season too")
elif favorite_season == "Summer":
    print("Summer is amazing")
elif favorite_season == "Spring":
    print("I love spring")
else:
    print("Fall is my mom's favorite season")
Each condition will be checked and only the code block of the first condition that evaluates to True will run. If none of them are True, the else clause will run.
