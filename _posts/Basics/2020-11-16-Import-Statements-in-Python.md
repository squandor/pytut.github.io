---
layout: page
#
# Content
#
subheadline: "Import Statements in Python"
title: "Import Statements in Python"
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
Organizing your code into multiple files as your program grows in size and complexity is good practice. But we need to find a way to combine these files to make the program work correctly, and that is exactly what import statements do.
By writing an import statement, we can import a module (a file that contains Python definitions and statements) into another file.
These are various alternatives for import statements:
First Alternative:
import <module_name>
For example:
import math
If we use this import statement, we will need to add the name of the module before the name of the function or element that we are referring to in our code: 
>>> import math
>>> math.sqrt(25)
5.0
We explicitly mention in our code the module that the element belongs to.
Second Alternative:
import <module> as <new_name>
For example:
import math as m
In our code, we can use the new name that we assigned instead of the original name of the module:
>>> import math as m
>>> m.sqrt(25)
5.0
Third Alternative:
from <module_name> import <element>
For example:
from math import sqrt
With this import statement, we can call the function directly without specifiying the name of the module:
>>> from math import sqrt
>>> sqrt(25)
5.0
Fourth Alternative:
from <module_name> import <element> as <new_name>
For example:
from math import sqrt as square_root
With this import statement, we can assign a new name to the element imported from the module:
>>> from math import sqrt as square_root
>>> square_root(25)
5.0
Fifth Alternative:
from <module_name> import *
This statement imports all the elements of the module and you can refer to them directly by their name without specifying the name of the module. 
For example:
>>> from math import *

>>> sqrt(25)
5.0

>>> factorial(5)
120

>>> floor(4.6)
4

>>> gcd(5, 8)
1
According to the Style Guide for Python Code:
Wildcard imports (from <module> import *) should be avoided, as they make it unclear which names are present in the namespace, confusing both readers and many automated tools.