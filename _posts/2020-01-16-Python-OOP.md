------------------
layout: page 
title: Python (3) OOP
subtitle: It's here to help!
----------------
First, some background:

# What Computers Do
Generally, computers take data as input, follow algorithms, and produce data as output.

# Data
Generally, data must be held for a while during execution of the algorithm. Python uses variables to store data.

```
>>> 123
>>> foo = 7
```
## Data Types
Data comes in a number of types:

### Atomic (can't be split into smaller parts)
```
>>> foo = 7    # integer
>>> goo = 3.14 # float (floating point integer)
>>> hoo = "z"  # string (Python has no separate type for 'character')
```

### Structured
```
>>> koo = "My hovercraft is full of eels." # string of characters
>>> moo = [2, 13, 474]                     # list (of numbers)
>>> noo = [5, "bob", 6.02, "doggy"]        # list with more than one type of element
>>> qoo = (1,2,45)                         # tuple (as in 'double', 'quadruple', '7-tuple')
>>> roo = ("frog", 14)                     # tuple with elements of different types
>>> soo = {8, 2048}                        # set
>>> too = {"dynomite", 7.62}               # set with elements of different types
>>> voo = {
```
### Deeper structure

```
>>> woo = [5.56, (2, 4, "Burrito"), ["a", 1723], "klingon"] # list with structures as elements
```

Putting data into complex structures, especially if they (as often) are uniform in shape, can get boring, should be automated where possible, and computers can be used for this.

# Objects and Object-Oriented Programming (OOP)
Predefined structures for data can be defined and used. Most computer languages refer to
- these standardized structures as **objects**
- the structure definitions (not the concrete objects, more like the blueprints) as **classes**
- the process of creating an object of a class as **instantiation**
- one specific object as an **instance** of a class
- pieces of data held in Objects as **attributes**
- ways of doing things to the attributes held in objects, or ways of doing things using attributes as inputs, as **methods**
- Programming making use of this way of organizing and using data is **Object-Oriented Programming**.

## Object-Oriented Programming in Python
In Python, to define a class: (this one is as simple as possible, and is useless other than counting, since it does not have any attributes or methods)

### Define a class
We can define a class very simply.

```
class ScaryAnimal:
    pass
```
**class** is a keyword. Capitalization is exact. Followed by a semicolon.

**ScaryAnimal** is a name, and, by convention, is **CamelCase** (**LikeTheseWordsHere**)

**pass** is Python placeholder code. We really should add methods and attributes.

### Make an object of that class
We can make ('instantiate') one (at the REPL, or in stored code)

```
my_first_monster = ScaryAnimal() # make me a scary animal, and store that in the variable 'my_first_monster'
my_first_monster # let's see what Python thinks my_first_monster is
```

**```__main__.```** means that **ScaryAnimal** is a 'top-level' class

**```object```** means **my_first_monster** is a Python object

The hex number like (but this can vary every time we run code) **```0x7fef14a46410```** is the address, in memory, where **my_first_monster** starts.

### Make the object so that it can store some useful information

**```__init__```**
This is a method, which is a function specialized on a class.

```__init__``` is a special class, and that is what the underscores are there to indicate.

When Python instantiates a class (makes an object of that class), Python looks for a method named ```__init__```, and, if Python finds it, executes the code therein.

```__init__``` is also called the constructor method, but I think this is a little off.

We can create objects without ```__init__``` being defined (so without being found by Python).

If ```__init__``` is found (and we should create one, at least for top-level classes) it
- creates attributes (I think of them as named slots), and
- gives these attributes initial values.

To be clear, we did, in fact, create **my_first_monster** without an ```__init__``` method, so it is possible. Just not particularly useful, except if we just want to count monsters.

## Attributes
Attributes are variables specialized on each object. If each monster has an attribute like number_of_eyes, we can have different monsters with different numbers of eyes.

Attributes (named slots that belong to a specific object) are created, and given an initial value by, ```__init__```.

If we want to specify, at the time we create a new object, the value of some attribute of the new object (e.g., eye_count = 8, or has_fangs = True) we can identify the parameters we must pass when instantiating this class.

## A Second Class
```
class ScarierAnimal:
 
    def __init__(self, number_of_eyes, has_fangs): 
        self.number_of_eyes = number_of_eyes
        self.has_fangs = has_fangs
```

**self** is used to refer to the new object we are building, so we can use Python code to manipulate that new object.

Even though we have defined an ```__init__``` for **ScarierAnimal**, We can still instantiate an object of type **ScarierAnimal** without having it assigned any attributes.

**(I do not think this is good.)**

```
>>> my_second_monster = ScarierAnimal
>>> my_second_monster.number_of_eyes
ERROR
```
But, now that we have defined ```__init__```, taking two parameters, we can instantiate a **ScarierAnimal** by passing values, like so:

```
>>> my_third_monster = ScarierAnimal(16, False)
>>> my_third_monster.number_of_eyes
16
```

**Note** that, in our definition of ```__init__```, there are three parameters. The first one, **self**, however, is special. It is automatically assigned the value of the object itself, so we do not (and better not try to) pass a value via self.

**Note** the names of the parameters on the right side of assignments like
```
        self.eye_count = eye_count
```
do not need to match the names of the attributes on the left side.

**ALSO NOTE that they conventionally do.**

## A Silly Class

```
# This would work, but would be silly:

class ScaryAnimalOdd:
  def __init__(self, darth, leia):
    self.eye_count = darth
    self.has_fangs = leia
    
```
```
>>> critter_2 = ScaryAnimalOdd(3, False)
>>> critter_2.eye_count
3
```

## More about Methods
Methods are functions for changing or using values held in attributes. They are specified as part of the class definition, and so apply to every instance of that class.

Perhaps we know that monsters sometimes lose eyes, and sometimes must be defanged.

We can define a couple of methods as part of a class.

```
    def defang(self):
        self.has_fangs = False
 
    def poke_eye_out(self):
        self.eye_count = self.eye_count - 1
```

Like in a class definition

```
class EvenMoreScaryAnimal:
 
    def __init__(self, number_of_eyes, has_fangs): 
        self.number_of_eyes = number_of_eyes
        self.has_fangs = has_fangs
        
    def defang(self):
        self.has_fangs = False
 
    def poke_eye_out(self):
```

```
>>> my_fourth_monster = EvenMoreScaryAnimal(6, True)
>>> my_fourth_monster.number_of_eyes # no parens, so we want to learn about the **attribute** 'eye_count'
6
```

```
>>>my_fourth_monster.has_fangs 
True
```
```
>>> my_fourth_monster.poke_eye_out()
>>> my_fourth_monster.number_of_eyes
5
```
**Notes:**

- the parentheses indicate that we are invoking a function/method.
- even though self is a parameter in the definition of methods, no value is ever expected to be passed via self, and one (the special one of the object being called, like a leash) is what self evaluates to within the method definition.

## Sub-Classes
Often making sub-classifications is useful, because, although objects in a sub-class (like SportsCar) might share attributes (engine_model) and methods with (add_miles()) with a parent class (like MotorVehicle), they might also have different attributes or methods (racing_league).

We can efficiently capture this by creating subclasses.

# EDITING BELOW HERE
