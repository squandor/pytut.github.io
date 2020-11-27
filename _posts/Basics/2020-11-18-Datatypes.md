---
layout: page
#
# Content
#
subheadline: "Datatypes"
title: "The common datatypes in python"
teaser: "Python has a lot of different datatypes which you will encounter so lets start with the most common used."
categories:
  - Basics
tags:
  - Python
  - Datatypes
  - Basics
  - Examples
#
# Styling
#
header: no
mediaplayer: false
comments: true
---

Inside python you have different datatypes which you can use or will encounter. 
The basic/most often datatypes are:
- String
- Integer
- Float
- List
- Dictionary

But before we will see what different options each datatype has you first need to know some things:
- First, what are comments?. 
A Comment is just some kind of text which will not be run by python but will make youre life easier if you learn from the start to use it.
You can use comments to explain what a line or piece of code does inside the program.
Every Comment inside python starts with an # 
But beware, if you read further i will show you some examples where a peace of code looks like an comment but really isn't. 
- Second, what are variables?.
A variable is an piece of memory which you can reserve to save data on the fly. In my examples i always start my variables with an underscore _. 
Its not needed but this way i always know which codes are variables. 
To save some kind of info to an variable you first need to give the variable a name and follow that name with an = 

For example:
{% highlight python %}
_hello = 
{% endhighlight %}

So the name of the variable is _hello and with the = i said that everything that comes next will be put inside _hello, be aware that at this point the "datatype" of the variable 
is still nothing. That will change depending on the data you will use after the = 

So lets start first with the datatypes:
## String
Simple said an String is not an piece of underware but a piece of text inside python. If you want to create an string you simple use quotes around some text. 
So lets say i want to create an string with the words Hello World inside of it i can simple say:
{% highlight python %}
'Hello World'
{% endhighlight %}
or
{% highlight python %}
"Hello World"
{% endhighlight %}

Python will see both examples as an String. 
So if i want to save the string "Hello World" to the variable _hello you can simply use:
{% highlight python %}
_hello = 'Hello World'  # saving string to variable
print(_hello)           # Print variable to console
{% endhighlight %}

In this example i saved the string "Hello World" to the variable _hello and on the second line i wrote that i want to print the variable to the console to check if the text
is really saved to the variable. 

## Integer
An int/integer is the definition of a whole number. The number can be positive or negative but there are no decimals. 
The most simple way to set a integer to an variable is:
{%highlight python %}
_x = 1
_y = 2
_z = 123

print (_x)
print (type(_x))

{% endhighlight %}

So in this example i saved the number 1 to x, 2 to y and 123 to z. After that i printed the value of x and printed on the next line the type of the variable which will say Integer

You can do all sort of things with an integer. You can count inside a loop or make an calculation with different numbers like:
{% highlight python %}
_x = 1 + 2
_y = 2 + 3
_z = x + y

print (_z)
{% endhighlight %}
So here you can see that inside x = 3 because i did 1 + 2. the same goes for y. 
and with z i summed up x + y which will resolve into 8: z = 3 + 5

## Float
Floats looks simmilar to an integer except it will allow you to use one or more decimals. 
{% highlight python %}
_x = 1.50
_y = 1.1
print (type(_x))
print (type(_y))
{% endhighlight %}
So this will automatically result in floats because of the decimals. 

## List
A list is used to store multiple items inside a variable, there are different kind of lists inside python and a little bit further i will show the use of an dictionary
But a normal list can be created using the brackets. 
{% highlight python %}
_list = ["dog", "cat", 'fish']
print (_list)
{% endhighlight %}

So in this example i created an list called _list and inside are 3 value's. a Dog, Cat and a Fish. Did you see that i didn't use the " for fish. 
It maybe can bee sloppy but i will not give you an error. Like i said at the topic Strings you can define them by using " or '

So we have an list of animals now, each animal has in "index" inside this list. A computer always starts counting with a 0 so in python we start with that to. 
for example, if you want to print just dog you can do:
{% highlight python %}
_list = ["dog", "cat", 'fish']
print (_list[0])
{% endhighlight %}
Because dog is the first animal inside the list. You can print the second item "Cat" with _list[1]

I only used Strings for this list, but you can use all sort of datatypes to put inside an list like numbers or boolean types (true/false)

Here are some examples about what you can do with a list:
{% highlight python %}
_list = ["dog", "cat", 'fish']
print (_list)                       
_list = sort(_list)                 # Sort the list alphabetically 
print (_list)                       # print the list again.

_counter = 0                        # create an integer variable with 0 inside
for i in _list:                     # start a for loop on the list 
    print(i)                        # print the item
    _counter += 1                   # add 1 to the _counter variable

print (_counter)                    # print the _counter
print (len(_list))                  # print the length of the list with the function len()

_list.append("bunny")               # add the animal "bunny" to the list.
print (_list)                       # print the new list.
print (len(_list))                  # print the new length of the list.

_list_int = [9,8,7,6,5,4,3,2,1,1,0] # create an list with 11 numbers.
_list_bool = [True, False, False]   # create an list with boolean values.
_list_chaos = [1,"cha", True, "os"] # create an list with different data types.
{% endhighlight %}

## Dictionary
A dictionary is simmilar to an list but within an dictionary you store datavalues in key:value pairs. 
The dictionary object at default will be unordered, can be changed but will not allow duplicates. 
To create an dictionary you use the curly brackets and make use of an key and value pair:
{% highlight python %}
_dict = {
    "device": "laptop",
    "model": "Macbook Pro",
    "brand": "Apple",
    "year": 2014
}
print (_dict)
{% endhighlight %}

So here i created an dictionary called _dict and added different pairs to it, device:laptop, model:macbook pro, brand:apple, year:2014 
So to use these values you can just use:
{% highlight python %}
_dict = {
    "device": "laptop",
    "model": "Macbook Pro",
    "brand": "Apple",
    "year": 2014
}
print (_dict['model'])
{% endhighlight %}
So instead of using the index number 0,1,2,3 you can use the key name to get the value. 
So lets use the list and dictionary together:
{% highlight python %}
_dict = {
    "device": "laptop",
    "model": "Macbook Pro",
    "brand": "Apple",
    "year": 2014,
    "options": ["retina display", "13 inch", "15 inch", "magic mouse"]
}
print (_dict)
{% endhighlight %}
So here i added an "list" to the key options with different strings inside of it. 
But you can also turn this around to save multiple dictionary's inside an list:
{% highlight python %}
_list = [{'device': 'laptop', 'model': 'macbook pro', 'brand': 'apple', 'year': 2014}, {'device': 'laptop', 'model': '250 G7', 'brand': 'HP', 'year': 2019}]
print (_list)
{% endhighlight %}
So here i added 2 dictionary's to a list. 

