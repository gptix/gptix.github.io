
# Table of Contents

1.  [Hoon School](#org0285a8c)
    1.  [Lesson One](#org56403e7)
    2.  [Glossary](#org4690766)
        1.  [Ace](#org33f9cda)
        2.  [Arm](#org96f65a5)
        3.  [Atom](#org830d46a)
        4.  [Aura](#org9583289)
        5.  [Buc](#org76eeceb)
        6.  [Casting](#org9b6efe4)
        7.  [Cell](#orgf900d4d)
        8.  [Children](#orgd6851e9)
        9.  [Core](#org43f4684)
        10. [Dojo](#org4d239ac)
        11. [Face](#org72627ed)
        12. [Gap](#org8e670e0)
        13. [Generator](#org19c2127)
        14. [Gate](#orgc3f9417)
        15. [Hoon](#org3a681d9)
        16. [Irregular Form](#orgdac5f0f)
        17. [Leg](#org0cbc3ca)
        18. [Mounting a pier](#org388afbd)
        19. [Noun](#orgbce289a)
        20. [Pier](#orgdf4992c)
        21. [Sample](#org9a6d6a3)
        22. [Spec](#org662d15a)
        23. [Wing](#orga4cad71)
    3.  [Error messages](#orgd239dda)
        1.  [nest-fail](#org0f54533)

&#x2014;
layout: page
title: Urbit and Hoon
subtitle: Escape the Ologopoly - Move to Urbit.
&#x2014;

Urbit is a clean-slate approach to computing, with an integrated stack from a single function, Nock, a programming language, Hoon, and operating system, Arvo. Virtual computers with permanent identities recorded on the Ethereum blockchain communicate via encrypted traffic over a network to other 'ships', be they 'planets', 'stars', 'galaxies', or 'comets'.

My planet is ~habnus-dovres.

Next steps:

-   [ ] complete hoon school
-   [ ] move planet to a server in a cloud


<a id="org0285a8c"></a>

# Hoon School


<a id="org56403e7"></a>

## Lesson One

generator
naked generator


<a id="org4690766"></a>

## Glossary


<a id="org33f9cda"></a>

### Ace

A single space used as one kind of delimiter in Hoon code.


<a id="org96f65a5"></a>

### Arm

A substructure of a Hoon that is a function to be applied to a Noun. Functions.


<a id="org830d46a"></a>

### Atom

A natural number.  These can be 'cast' (interpreted as) a vatiety of types, such as planet name, integer, float, character&#x2026;


<a id="org9583289"></a>

### Aura

A specification of the way Hoon (the language) should 'interpret' and operate on an atom.


<a id="org76eeceb"></a>

### Buc

An arm that is evaluated immediately. many types of Cores, including Gates, have a Buc, and it appears immediately after the Spec.


<a id="org9b6efe4"></a>

### Casting

Specification that a value (they are all just Nouns, consisting, deep down, of natural numbers) as some type of information, such as integer, float, character, list&#x2026;


<a id="orgf900d4d"></a>

### Cell

A pair of nouns. Displayed as [a b]


<a id="orgd6851e9"></a>

### Children

Arguments to an Arm.


<a id="org43f4684"></a>

### Core

A data structure that has one or more Arms.
'Something to do' paired with 'something with which to do it'.
A combinator and values to pass to the combinator.


<a id="org4d239ac"></a>

### Dojo

A Hoon REPL.


<a id="org72627ed"></a>

### Face

A symbol bound to a value. 
E.g., in 'a=2', 'a' is a face bound to the value 2.


<a id="org8e670e0"></a>

### Gap

Two consecutive spaces (or a carriage return) used as one kind of delimiter in Hoon code.


<a id="org19c2127"></a>

### Generator

Code stored in a file. Potentially a function to be applied to other input.


<a id="orgc3f9417"></a>

### Gate

A Core that has exactly one Spec followed by exactly one Hoon.


<a id="org3a681d9"></a>

### Hoon

A series of hoon (the language; this is an ovrloading of the word 'hoon') expressions that terminate (meaning they evaluate to a concrete value, needing no further evaluation &#x2013; having no opportunity for further evaluation.


<a id="orgdac5f0f"></a>

### Irregular Form

An exception to normal syntax used for structural convenience, and in some cases for abbreviation.


<a id="org0cbc3ca"></a>

### Leg

A subtructure of a Hoon that is 'only' data to be consumed by an Arm. Static data.


<a id="org388afbd"></a>

### Mounting a pier

The process of linking a directory structure of a ship to a unix(y) file system.


<a id="orgbce289a"></a>

### Noun

An atom or a cell


<a id="orgdf4992c"></a>

### Pier

A point, in a filesystem on a server, to which an Urbit ship is mounted.
Often at ~/urbit/~some-ship/ 


<a id="org9a6d6a3"></a>

### Sample

Information, structured as a Hoon, that contains values that are passed to Arms as values for parameters specified in Specs.


<a id="org662d15a"></a>

### Spec

A noun that contains information indicating the Type that information received should be interpreted as.


<a id="orga4cad71"></a>

### Wing

A category comprising Arms and Legs.


<a id="orgd239dda"></a>

## Error messages


<a id="org0f54533"></a>

### nest-fail

Indicates a type mismatch between an input value and the type of input expected by a function.

calling a gate
dojo
runes

Pronunciation guide
Atomic auras

