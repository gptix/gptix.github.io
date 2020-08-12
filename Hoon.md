---
layout: page
title: Urbit and Hoon
subtitle: Escape the Ologopoly - Move to Urbit.
---

Urbit is a clean-slate approach to computing, with an integrated stack from a single function, Nock, a programming language, Hoon, and operating system, Arvo. Virtual computers with permanent identities recorded on the Ethereum blockchain communicate via encrypted traffic over a network to other 'ships', be they 'planets', 'stars', 'galaxies', or 'comets'.

My planet is ~habnus-dovres.

Next steps:

-   [ ] complete hoon school
-   [ ] move planet to a server in a cloud


<a id="orgc3238b7"></a>

# Hoon School


<a id="orgc73140f"></a>

## Lesson One

generator
naked generator


<a id="org373c1fd"></a>

## Glossary


<a id="org8b432b9"></a>

### Ace

A single space used as one kind of delimiter in Hoon code.


<a id="orgf6b4039"></a>

### Arm

A substructure of a Hoon that is a function to be applied to a Noun. Functions.


<a id="orgef2349d"></a>

### Atom

A natural number.  These can be 'cast' (interpreted as) a vatiety of types, such as planet name, integer, float, character&#x2026;


<a id="org970477c"></a>

### Aura

A specification of the way Hoon (the language) should 'interpret' and operate on an atom.


<a id="org1810489"></a>

### Buc

An arm that is evaluated immediately. many types of Cores, including Gates, have a Buc, and it appears immediately after the Spec.


<a id="org68de56e"></a>

### Casting

Specification that a value (they are all just Nouns, consisting, deep down, of natural numbers) as some type of information, such as integer, float, character, list&#x2026;


<a id="org036b593"></a>

### Cell

A pair of nouns. Displayed as [a b]


<a id="orgb8bac7d"></a>

### Children

Arguments to an Arm.


<a id="org0bbbcde"></a>

### Core

A data structure that has one or more Arms.
'Something to do' paired with 'something with which to do it'.
A combinator and values to pass to the combinator.


<a id="org3878991"></a>

### Dojo

A Hoon REPL.


<a id="org6a47475"></a>

### Face

A symbol bound to a value. 
E.g., in 'a=2', 'a' is a face bound to the value 2.


<a id="orga49de9e"></a>

### Gap

Two consecutive spaces (or a carriage return) used as one kind of delimiter in Hoon code.


<a id="orge133b6f"></a>

### Generator

Code stored in a file. Potentially a function to be applied to other input.


<a id="orgb9ead37"></a>

### Gate

A Core that has exactly one Spec followed by exactly one Hoon.


<a id="orgdf11460"></a>

### Hoon

A series of hoon (the language; this is an ovrloading of the word 'hoon') expressions that terminate (meaning they evaluate to a concrete value, needing no further evaluation &#x2013; having no opportunity for further evaluation.


<a id="org02dce4a"></a>

### Irregular Form

An exception to normal syntax used for structural convenience, and in some cases for abbreviation.


<a id="org2da281e"></a>

### Leg

A subtructure of a Hoon that is 'only' data to be consumed by an Arm. Static data.


<a id="org59e438e"></a>

### Mounting a pier

The process of linking a directory structure of a ship to a unix(y) file system.


<a id="orgc027d40"></a>

### Noun

An atom or a cell


<a id="org04c9937"></a>

### Pier

A point, in a filesystem on a server, to which an Urbit ship is mounted.
Often at ~/urbit/~some-ship/ 


<a id="orgc52876c"></a>

### Sample

Information, structured as a Hoon, that contains values that are passed to Arms as values for parameters specified in Specs.


<a id="org9ead115"></a>

### Spec

A noun that contains information indicating the Type that information received should be interpreted as.


<a id="org7e210d0"></a>

### Wing

A category comprising Arms and Legs.


<a id="org4c8215a"></a>

## Error messages


<a id="orgb2688ea"></a>

### nest-fail

Indicates a type mismatch between an input value and the type of input expected by a function.

calling a gate
dojo
runes

Pronunciation guide
Atomic auras

