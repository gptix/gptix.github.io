---
layout: page
title: Python (3) OOP
subtitle: It's here to help!
---

First, some background:

# What Computers Do
Generally, computers take data as input, follow algorithms, and produce data as output.

# Data
Generally, data must be held for a while during execution of the algorithm. Python uses variables to store data.

```
>>> foo = 7
>>>
>>> foo
7
```

## Data Types
Data comes in a number of types:

### Atomic (can't be split into smaller parts)

```
foo = 7    # integer
goo = 3.14 # float (floating point integer)
hoo = "z"  # string (Python has no separate type for 'character')
```

### Structured

```
koo = "My hovercraft is full of eels." # string of characters
moo = [2, 13, 474]                     # list (of numbers)
noo = [5, "bob", 6.02, "doggy"]        # list with more than one type of element
qoo = (1,2,45)                         # tuple (as in 'double', 'quadruple', '7-tuple')
roo = ("frog", 14)                     # tuple with elements of different types
soo = {8, 2048}                        # set
too = {"dynomite", 7.62}               # set with elements of different types
voo = {"Captain" : "Tennielle", "Johnny" : "Sid"}        # dictionary (set of 'key': 'value' pairs)
```

### Deeper structure

```
woo = [5.56, (2, 4, "Burrito"), ["a", 1723], "klingon"] # list with structures as elements
```

Putting data into complex structures, especially if they (as often) are uniform in shape, can get boring, should be automated where possible, and computers can be used for this.

### **Objects** and **Object-Oriented Programming** (**OOP**)

Predefined structures for data can be defined and used. Most computer languages refer to 
- these standardized structures as **objects**
- the structure definitions (not the concrete objects, more like the blueprints) as **classes**
- the process of creating an object of a class as **instantiation**
- one specific object as an **instance** of a class
- pieces of data held in Objects as **attributes**
- ways of doing things to the attributes held in objects, or ways of doing things using attributes as inputs, as **methods**

Programming making use of this way of organizing and using data is **Object-Oriented Programming**.

# Object-Oriented Programming in Python
In Python, to define a class: (this one is as simple as possible, and is useless, since it does not have any attributes or methods)

## Define a class
```
Class ScaryAnimal:
    pass 
```
**Class** is a keyword. Capitalization is exact. Followed by a semicolon.

**ScaryAnimal** is a name, and, by convention, is **CamelCase** (**LikeTheseWordsHere**)

**pass** is Python placeholder code. We really should add methods and attributes.

## Make an object of that class
We can make ('instantiate') one (at the REPL, or in stored code)

```
>>> my_first_monster = ScaryAnimal() # make me a scary animal, and store that in the variable 'my_first_monster'
>>> my_first_monster # let's see what Python thinks my_first_monster is
<__main__.ScaryAnimal object at 0x7fef14a46410>
```

**__main__.** means that ScaryAnimal is a 'top-level' class

**object** means it is a Python object

**0x7fef14a46410** is the address, in memory, where my_first_monster starts. The exact number will vary.

## Make the object so that it can store some useful information

### Parameters

### ```__init__```


This is a **method** that is used to make an instance according to a blueprint. The double underscores are used to indicate that the method is *special*. Do not (unless you really need to, and you will know) name things with double-underscores leading or trailing.

Python, when making a new object, automatically looks for a method named ```__init__``` inside that class' definition. then, Python runs that method.

We will add, inside the definition of the class, code like this:

```
Class ScaryAnimal:
     
    def __init__(self):
        print("A new scary animal arises!.")
```

**self** is used to refer to the new object we are building, so we can use Python code to manipulate that new object.

Our code is pretty simple, since we have no information about anything that is specific to this new object. 

### Specifying Values for Attributes of New Objects

If we want to specify, at the time we create a new object, the value of some attribute of the new object (e.g., eye_count = 8, or has_fangs = True) we can identify the **parameters** we must pass when instantiating this class.


**Note: my notes a couple of hours ago mistakenly had parameters in parentheses just after the class name. Wrong.**

```
class ScaryAnimal:

    def __init__(self):
        self.eye_count = eye_count
	    self.has_fangs = has_fangs
	
```

**Note** the names of the parameters on the **right** side of assignments like

```
	    self.eye_count = eye_count
```

do not need to match the names of the **attributes** on the left side.

**ALSO NOTE** that they conventionally do.

This would work, but would be silly:
```
class ScaryAnimalOdd:

    def __init__(self, darth, leia):
	    self.eye_count = darth
        self.has_fangs = leia
	
```
at a REPL
```
>>> critter_2 = ScaryAnimalOdd(3, False)
>>> critter_2.eye_count
3
```

# Editing below here


### Methods

**Methods** are functions for changing or using values held in attributes. They are specified as part of the **class** definition, and so apply to every instance of that class.


```
    def defang(self):
        self.has_fangs = False
		
    def poke_eye_out(self):
        self.eye_count = self.eye_count - 1
```

One of these might be called like this:

```
>>> my_critter = ScaryAnimal(6, True)
>>> my_critter.eye_count # no parens, so we want to learn about the **attribute** 'eye_count'
6
>>> my_critter.poke_eye_out() # the parentheses make this a call to a method
>>> my_critter.eye_count
5
```

**Note** methods are often used to manage values for an object after it is instantiated. We might give an account object a nice balance when we create a new account (object), then use methods to 
### Overriding

## Making more specific classes

### Overriding parent class stuff

#### Attributes

#### Methods
