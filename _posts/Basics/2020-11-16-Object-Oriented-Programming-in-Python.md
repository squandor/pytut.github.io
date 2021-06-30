---
layout: page
#
# Content
#
subheadline: "Object-Oriented Programming in Python"
title: "Object-Oriented Programming in Python"
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

In Object-Oriented Programming (OOP), we define classes that act as blueprints to create objects in Python with attributes and methods (functionality associated with the objects).
This is a general syntax to define a class:
{% highlight python %}
class <className>:

    <class_attribute_name> = <value>

    def __init__(self,<param1>, <param2>, ...):
        self.<attr1> = <param1>
        self.<attr2> = <param2>
        .
        .
        .
        # As many attributes as needed
    
   def <method_name>(self, <param1>, ...):
       youre code
       
   # As many methods as needed
{% endhighlight %}

As you can see, a class can have many different elements so let's analyze them in detail:
Class Header
The first line of the class definition has the {% highlight python %}
class
{% endhighlight %}
 keyword and the name of the class:
{% highlight python %}
class Dog:
{% endhighlight %}

{% highlight python %}
class House:

{% endhighlight %}

{% highlight python %}
class Ball:
{% endhighlight %}

{% highlight python %}
class Poodle(Dog):
{% endhighlight %}

{% highlight python %}
class Truck(Vehicle):
{% endhighlight %}

{% highlight python %}
class Mom(FamilyMember):
{% endhighlight %}

In Python, we write class name in Upper Camel Case (also known as Pascal Case), in which each word starts with an uppercase letter. For example: {% highlight python %}
FamilyMember
{% endhighlight %}

{% highlight python %}
__init__
{% endhighlight %}
 and instance attributes
We are going to use the class to create object in Python, just like we build real houses from blueprints. 
The objects will have attributes that we define in the class. Usually, we initialize these attributes in {% highlight python %}
__init__
{% endhighlight %}
. This is a method that runs when we create an instance of the class. 
This is the general syntax:
{% highlight python %}
def __init__(self, <parameter1>, <parameter2>, ...):
        self.<attribute1> = <parameter1>  # Instance attribute
        self.<attribute2> = <parameter2>  # Instance attribute
        .
        .
        .
        # As many instance attributes as needed
{% endhighlight %}

We specify as many parameters as needed to customize the values of the attributes of the object that will be created.
Here is an example of a {% highlight python %}
Dog
{% endhighlight %}
 class with this method:
{% highlight python %}
class Dog:

    def __init__(self, name, age):
        self.name = name
        self.age = age
{% endhighlight %}

How to Create an Instance
To create an instance of {% highlight python %}
Dog
{% endhighlight %}
, we need to specify the name and age of the dog instance to assign these values to the attributes:
{% highlight python %}
my_dog = Dog("Nora", 10)
{% endhighlight %}

Great. Now we have our instance ready to be used in the program.
Some classes will not require any arguments to create an instance. In that case, we just write empty parentheses. For example:
{% highlight python %}
class Circle:

    def __init__(self):
        self.radius = 1
{% endhighlight %}

To create an instance:
{% highlight python %}
>>> my_circle = Circle()
{% endhighlight %}

Default Arguments
We can also assign default values for the attributes and give the option to the user if they would like to customize the value.
In this case, we would write {% highlight python %}
<attribute>=<value>
{% endhighlight %}
 in the list of parameters. 
This is an example:
{% highlight python %}
class Circle:

    def __init__(self, radius=1):
        self.radius = radius
{% endhighlight %}

Now we can create a {% highlight python %}
Circle
{% endhighlight %}
 instance with the default value for the radius by omitting the value or customize it by passing a value:
{% highlight python %}
# Default value
>>> my_circle1 = Circle()

# Customized value
>>> my_circle2 = Circle(5)
{% endhighlight %}

How to Get an Instance Attribute
To access an instance attribute, we use this syntax:
{% highlight python %}
<object_variable>.<attribute>
{% endhighlight %}

For example:
{% highlight python %}
# Class definition
>>> class Dog:

    def __init__(self, name, age):
        self.name = name
        self.age = age

# Create instance        
>>> my_dog = Dog("Nora", 10)

# Get attributes
>>> my_dog.name
'Nora'

>>> my_dog.age
10
{% endhighlight %}

How to Update an Instance Attribute
To update an instance attribute, we use this syntax:
{% highlight python %}
<object_variable>.<attribute> = <new_value>
{% endhighlight %}

For example:
{% highlight python %}
>>> class Dog:

    def __init__(self, name, age):
        self.name = name
        self.age = age

        
>>> my_dog = Dog("Nora", 10)

>>> my_dog.name
'Nora'

# Update the attribute
>>> my_dog.name = "Norita"

>>> my_dog.name
'Norita'
{% endhighlight %}

How to Remove an Instance Attribute
To remove an instance attribute, we use this syntax:
{% highlight python %}
del <object_variable>.<attribute>
{% endhighlight %}

For example:
{% highlight python %}
>>> class Dog:

    def __init__(self, name, age):
        self.name = name
        self.age = age

        
>>> my_dog = Dog("Nora", 10)

>>> my_dog.name
'Nora'

# Delete this attribute
>>> del my_dog.name

>>> my_dog.name
Traceback (most recent call last):
  File "<pyshell#77>", line 1, in <module>
    my_dog.name
AttributeError: 'Dog' object has no attribute 'name'
{% endhighlight %}

How to Delete an Instance
Similarly, we can delete an instance using {% highlight python %}
del
{% endhighlight %}
:
{% highlight python %}
>>> class Dog:

    def __init__(self, name, age):
        self.name = name
        self.age = age

        
>>> my_dog = Dog("Nora", 10)

>>> my_dog.name
'Nora'

# Delete the instance
>>> del my_dog

>>> my_dog
Traceback (most recent call last):
  File "<pyshell#79>", line 1, in <module>
    my_dog
NameError: name 'my_dog' is not defined
{% endhighlight %}

Public vs. Non-Public Attributes in Python
In Python, we don't have access modifiers to functionally restrict access to the instance attributes, so we rely on naming conventions to specify this.
For example, by adding a leading underscore, we can signal to other developers that an attribute is meant to be non-public. 
For example:
{% highlight python %}
class Dog:

    def __init__(self, name, age):
        self.name = name  # Public attribute
        self._age = age   # Non-Public attribute
{% endhighlight %}

The Python documentation mentions:
Use one leading underscore only for non-public methods and instance variables. Always decide whether a class's methods and instance variables (collectively: "attributes") should be public or non-public. If in doubt, choose non-public; it's easier to make it public later than to make a public attribute non-public.Non-public attributes are those that are not intended to be used by third parties; you make no guarantees that non-public attributes won't change or even be removed. - source
However, as the documentation also mentions:
We don't use the term "private" here, since no attribute is really private in Python (without a generally unnecessary amount of work). - source
Class Attributes in Python
Class attributes are shared by all instances of the class. They all have access to this attribute and they will also be affected by any changes made to these attributes.
{% highlight python %}
class Dog:

    # Class attributes
    kingdom = "Animalia"
    species = "Canis lupus"

    def __init__(self, name, age):
        self.name = name
        self.age = age
{% endhighlight %}

How to Get a Class Attribute
To get the value of a class attribute, we use this syntax:
{% highlight python %}
<class_name>.<attribute>
{% endhighlight %}

For example:
{% highlight python %}
>>> class Dog:

    kingdom = "Animalia"

    def __init__(self, name, age):
        self.name = name
        self.age = age

        
>>> Dog.kingdom
'Animalia'
{% endhighlight %}

How to Update a Class Attribute
To update a class attribute, we use this syntax:
{% highlight python %}
<class_name>.<attribute> = <value>
{% endhighlight %}

For example:
{% highlight python %}
>>> class Dog:

    kingdom = "Animalia"

    def __init__(self, name, age):
        self.name = name
        self.age = age

        
>>> Dog.kingdom
'Animalia'

>>> Dog.kingdom = "New Kingdom"

>>> Dog.kingdom
'New Kingdom'
{% endhighlight %}

How to Delete a Class Attribute
We use {% highlight python %}
del
{% endhighlight %}
 to delete a class attribute. For example:
{% highlight python %}
>>> class Dog:

    kingdom = "Animalia"

    def __init__(self, name, age):
        self.name = name
        self.age = age

>>> Dog.kingdom
'Animalia'
        
# Delete class attribute
>>> del Dog.kingdom

>>> Dog.kingdom
Traceback (most recent call last):
  File "<pyshell#88>", line 1, in <module>
    Dog.kingdom
AttributeError: type object 'Dog' has no attribute 'kingdom'
{% endhighlight %}

How to Define Methods
Methods represent the functionality of the instances of the class.
This is the basic syntax of a method in a class. They are usually located below {% highlight python %}
__init__
{% endhighlight %}
: 
{% highlight python %}
class <ClassName>:

    # Class attributes

    # __init__

    def <method_name>(self, <param1>, ...):
        youre code
{% endhighlight %}

They may have zero, one, or more parameters if needed (just like functions!) but instance methods must always have {% highlight python %}
self
{% endhighlight %}
 as the first parameter.
For example, here is a {% highlight python %}
bark
{% endhighlight %}
 method with no parameters (in addition to {% highlight python %}
self
{% endhighlight %}
):
{% highlight python %}
class Dog:

    def __init__(self, name, age):
        self.name = name
        self.age = age

    def bark(self):
        print(f"woof-woof. I'm {self.name}")
{% endhighlight %}

To call this method, we use this syntax:
{% highlight python %}
<object_variable>.<method>(<arguments>)
{% endhighlight %}

For example:
{% highlight python %}
# Create the instance
>>> my_dog = Dog("Nora", 10)

# Call the method
>>> my_dog.bark()
woof-woof. I'm Nora
{% endhighlight %}

Here we have a {% highlight python %}
Player
{% endhighlight %}
 class with an {% highlight python %}
increment_speed
{% endhighlight %}
 method with one parameter:
{% highlight python %}
class Player:

    def __init__(self, name):
        self.name = name
        self.speed = 50

    def increment_speed(self, value):
        self.speed += value
{% endhighlight %}

To call the method:
{% highlight python %}
# Create instance        
>>> my_player = Player("Nora")

# Check initial speed to see the change
>>> my_player.speed
50

# Increment the speed
>>> my_player.increment_speed(5)

# Confirm the change
>>> my_player.speed
55
{% endhighlight %}

Properties, Getters and Setters in Python
Getters and setters are methods that we can define to get and set the value of an instance attribute, respectively. They work as intermediaries to "protect" the attributes from direct changes. 
In Python, we typically use properties instead of getters and setters. Let's see how we can use them.
To define a property, we write a method with this syntax:
{% highlight python %}
@property
def <property_name>(self):
    return self.<attribute>
{% endhighlight %}

This method will act as a getter, so it will be called when we try to access the value of the attribute.
Now, we may also want to define a setter:
{% highlight python %}
@<property_name>.setter
def <property_name>(self, <param>):
    self.<attribute> = <param>
{% endhighlight %}

And a deleter to delete the attribute:
{% highlight python %}
@<property_name>.deleter
def <property_name>(self):
    del self.<attribute>
{% endhighlight %}

This is an example:
{% highlight python %}
class Dog:

    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        return self._name

    @name.setter
    def name(self, new_name):
        self._name = new_name

    @name.deleter
    def name(self):
        del self._name
{% endhighlight %}

If we add descriptive print statements, we can see that they are called when we perform their operation:
{% highlight python %}
>>> class Dog:

    def __init__(self, name):
        self._name = name

    @property
    def name(self):
        print("Calling getter")
        return self._name

    @name.setter
    def name(self, new_name):
        print("Calling setter")
        self._name = new_name

    @name.deleter
    def name(self):
        print("Calling deleter")
        del self._name

        
>>> my_dog = Dog("Nora")

>>> my_dog.name
Calling getter
'Nora'

>>> my_dog.name = "Norita"
Calling setter

>>> my_dog.name
Calling getter
'Norita'

>>> del my_dog.name
Calling deleter
{% endhighlight %}

