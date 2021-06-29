---
layout: page
#
# Content
#
subheadline: "How to Work with Files in Python"
title: "How to Work with Files in Python"
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
Working with files is very important to create powerful programs. Let's see how you can do this in Python.
How to Read Files in Python
In Python, it's recommended to use a with statement to work with files because it opens them only while we need them and it closes them automatically when the process is completed.
To read a file, we use this syntax:
with open("<file_path>") as <file_var>:
    {% highlight python %}
We can also specify that we want to open the file in read mode with an "r":
with open("<file_path>", "r") as <file_var>:
    {% highlight python %}
But this is already the default mode to open a file, so we can omit it like in the first example.
This is an example:
with open("famous_quotes.txt") as file:
    for line in file:
        print(line)
or...
with open("famous_quotes.txt", "r") as file:
    for line in file:
        print(line)
How to Write to a File in Python
There are two ways to write to a file. You can either replace the entire content of the file before adding the new content, or append to the existing content.
with open("<file_path>", "w") as <file_var>:
    {% highlight python %}
To replace the content completely, we use the "w" mode, so we pass this string as the second argument to open(). We call the .write() method on the file object passing the content that we want to write as argument.
For example:
words = ["Amazing", "Green", "Python", "Code"]

with open("famous_quotes.txt", "w") as file:
    for word in words:
        file.write(word + "\n")
When you run the program, a new file will be created if it doesn't exist already in the path that we specified.
This will be the content of the file:
Amazing
Green
Python
Code
How to Append to a File in Python
However, if you want to append the content, then you need to use the "a" mode:
with open("<file_path>", "a") as <file_var>:
    {% highlight python %}

For example:
words = ["Amazing", "Green", "Python", "Code"]

with open("famous_quotes.txt", "a") as file:
    for word in words:
        file.write(word + "\n")
This small change will keep the existing content of the file and it will add the new content to the end.
If we run the program again, these strings will be added to the end of the file:
Amazing
Green
Python
Code
Amazing
Green
Python
Code

How to Delete a File in Python
To delete a file with our script, we can use the os module. It is recommended to check with a conditional if the file exists before calling the remove() function from this module:
import os

if os.path.exists("<file_path>"):
  os.remove("<file_path>")
else:
  {% highlight python %}
For example:
import os

if os.path.exists("famous_quotes.txt"):
  os.remove("famous_quotes.txt")
else:
  print("This file doesn't exist")
You might have noticed the first line that says import os. This is an import statement. Let's see why they are helpful and how you can work with them.