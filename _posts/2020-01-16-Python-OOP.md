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
foo = 7
```

## Data Types
Data comes in a number of types:

### Atomic (can't be taken apart into smaller parts)

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
>>> my_first_monster = ScaryAnimal() # make me a scary animal, and store that in the variable 'my_first_animal'
>>> my_first_monster # let's see what Python thinks my_first_monster is
<__main__.ScaryAnimal object at 0x7fef14a46410>
```

**__main__.** means that ScaryAnimal is a 'top-level' class

**object** means it is a Python object

**0x7fef14a46410** is the address, in memory, where my_first_monster starts. The exact number will vary.

## Make the object so that it can store some useful information

### Parameters

### ```__init__```

### Attributes

### Methods

### Overriding

## Making more specific classes

### Overriding parent class stuff

#### Attributes

#### Methods