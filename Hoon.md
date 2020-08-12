---
layout: page
title: Hoon Gossary
subtitle: Get the to Urbit!
---

I've gotten interested in Urbit.  Urbit is a network of virtual computers running on a stack starting with one function, Nock, through a programming language Hoon, an operating system called Arvo, to a network based on permanent identities that are planets, stars, and galaxies.

My planet is ~habnus-dovres.

Next steps:

- [ ] complete Hoon school

- [ ] move planet from laptop to AWS or Digital Ocean

# Table of Contents

1.  [Hoon School](#orgfa75edd)
    1.  [Lesson One](#org5932f26)
    2.  [Glossary](#org77d99c8)
        1.  [Ace](#org2dcf30b)
        2.  [Arm](#org10761e6)
        3.  [Atom](#org2cdecd3)
        4.  [Aura](#orgcab9140)
        5.  [Buc](#org793eff9)
        6.  [Casting](#org98a4cbb)
        7.  [Cell](#org281bffc)
        8.  [Children](#org2882bb5)
        9.  [Core](#org79d83ea)
        10. [Dojo](#orgf25e348)
        11. [Face](#orga24e4b8)
        12. [Gap](#orgc88c7e5)
        13. [Generator](#org669e1a9)
        14. [Gate](#org99a2c08)
        15. [Hoon](#org47cab68)
        16. [Irregular Form](#org886727f)
        17. [Leg](#orgcb2a5e7)
        18. [Mounting a pier](#org9fa4c82)
        19. [Noun](#org9ed7f04)
        20. [Pier](#orge540f44)
        21. [Sample](#orge986676)
        22. [Spec](#org6b0212d)
        23. [Wing](#org8ecdc01)
    3.  [Error messages](#org30d855c)
        1.  [nest-fail](#org448cc34)


<a id="orgfa75edd"></a>

# Hoon School


<a id="org5932f26"></a>

## Lesson One

generator
naked generator


<a id="org77d99c8"></a>

## Glossary


<a id="org2dcf30b"></a>

### Ace

A single space used as one kind of delimiter in Hoon code.


<a id="org10761e6"></a>

### Arm

A substructure of a Hoon that is a function to be applied to a Noun. Functions.


<a id="org2cdecd3"></a>

### Atom

A natural number.  These can be 'cast' (interpreted as) a vatiety of types, such as planet name, integer, float, character&#x2026;


<a id="orgcab9140"></a>

### Aura

A specification of the way Hoon (the language) should 'interpret' and operate on an atom.


<a id="org793eff9"></a>

### Buc

An arm that is evaluated immediately. many types of Cores, including Gates, have a Buc, and it appears immediately after the Spec.


<a id="org98a4cbb"></a>

### Casting

Specification that a value (they are all just Nouns, consisting, deep down, of natural numbers) as some type of information, such as integer, float, character, list&#x2026;


<a id="org281bffc"></a>

### Cell

A pair of nouns. Displayed as [a b]


<a id="org2882bb5"></a>

### Children

Arguments to an Arm.


<a id="org79d83ea"></a>

### Core

A data structure that has one or more Arms.
'Something to do' paired with 'something with which to do it'.
A combinator and values to pass to the combinator.


<a id="orgf25e348"></a>

### Dojo

A Hoon REPL.


<a id="orga24e4b8"></a>

### Face

A symbol bound to a value. 
E.g., in 'a=2', 'a' is a face bound to the value 2.


<a id="orgc88c7e5"></a>

### Gap

Two consecutive spaces (or a carriage return) used as one kind of delimiter in Hoon code.


<a id="org669e1a9"></a>

### Generator

Code stored in a file. Potentially a function to be applied to other input.


<a id="org99a2c08"></a>

### Gate

A Core that has exactly one Spec followed by exactly one Hoon.


<a id="org47cab68"></a>

### Hoon

A series of hoon (the language; this is an ovrloading of the word 'hoon') expressions that terminate (meaning they evaluate to a concrete value, needing no further evaluation &#x2013; having no opportunity for further evaluation.


<a id="org886727f"></a>

### Irregular Form

An exception to normal syntax used for structural convenience, and in some cases for abbreviation.


<a id="orgcb2a5e7"></a>

### Leg

A subtructure of a Hoon that is 'only' data to be consumed by an Arm. Static data.


<a id="org9fa4c82"></a>

### Mounting a pier

The process of linking a directory structure of a ship to a unix(y) file system.


<a id="org9ed7f04"></a>

### Noun

An atom or a cell


<a id="orge540f44"></a>

### Pier

A point, in a filesystem on a server, to which an Urbit ship is mounted.
Often at ~/urbit/~some-ship/ 


<a id="orge986676"></a>

### Sample

Information, structured as a Hoon, that contains values that are passed to Arms as values for parameters specified in Specs.


<a id="org6b0212d"></a>

### Spec

A noun that contains information indicating the Type that information received should be interpreted as.


<a id="org8ecdc01"></a>

### Wing

A category comprising Arms and Legs.


<a id="org30d855c"></a>

## Error messages


<a id="org448cc34"></a>

### nest-fail

Indicates a type mismatch between an input value and the type of input expected by a function.

calling a gate
dojo
runes

Pronunciation guide
Atomic auras

