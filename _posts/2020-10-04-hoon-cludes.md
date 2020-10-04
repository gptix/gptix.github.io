---
layout: post
title: Hoon-cludes
subtitle: It's Never Too Soon
---

## Enter Hoon School

[https://hooniversity.org/enroll/](https://hooniversity.org/enroll/)

Hoon is a functional, typed language. Using Hoon, we can write **gates** that can run directly on **Arvo**, the **Urbit** OS.

## Hoon School Teaches Many Things

- How to write and use gates
- Some data types
- Recursion
- More

## Including code modules

A key tactic in coding is to write code that performs a particular calculation based on inputs, then re-using that code as a building block.

Like in most languages, this modularization can be done in Urbit by storing code in libraries, then including them in other code.  This post explains how I tested this.

## How I did it:

##  Boot a fake planet.

I'd be daft to risk my home planet on sketchy code.

`bash $ ./urbit zod`

(a lot of line melody)

`~zod:dojo> `

## Make a first library.

```
:: A first library to test inclusion and use of libraries.
|%
++  addthree :: a function to be called   
  |=  x=@ud  ^-  @ud :: Take an unsigned integer, and return one.
  (add 3 x)
-- :: remember to close the gates.
```
Save this as `.../your-pier/home/lib/firstlib.hoon`

Note that libraries go in the subdirectory `lib`.

## So much fun! Again!

```
:: Another library to test inclusion and use of libraries.
|%
++  multwo :: a function to be called   
  |=  x=@ud  ^-  @ud :: Take an unsigned integer, and return one.
  (mul 2 x)
--
```
Save this as `.../your-pier/home/lib/secondlib.hoon`
  
## Make a gate that will use those two libraries.
```
:: Another generator to test inclusion and use of libraries.
|=  x=@ud  ^-  @ud

:: Include your libraries.
/+  firstlib  :: Include one library.
/+  secondlib :: Include a second library.
|=  x=@ud  ^-  @ud

:: To call an arm from a loaded library, the pattern is
:: (arm-name:library-name args)
(multwo:secondlib (addthree:firstlib x))
```
Save as  `.../your-pier/home/gen/twoincludes.hoon`

Note that this goes in the subdirectory `gen`


## Load code.

In **dojo**

```
~zod:dojo>  |commit %home :: load your new code from your pier into your ship.
>=
: /~zod/home/1.869/lib/firstlib/hoon
: /~zod/home/1.869/lib/secondlib/hoon
: /~zod/home/1.869/gen/twoincludes/hoon
```

*note* the '1.869' will likely be different. I think it is an event serial number.

## Test it out.

```
~zod:dojo> +twoincludes 2
10
```
**Success**

## Use your new skills!

I plan to create some libraries, making use of **lazytrig** by **~lagrev-nocfep**.

The first will be *the* **sigmoid** function.

## I've enjoyed my time here!

You all have been so wonderful!

It's never to soon to start learning Hoon!

See you on Mars!

**~habnus-dovres**

---
## Maybe of interest:

Urbit Overview  [https://youtu.be/M04AKTCDavc](https://youtu.be/M04AKTCDavc)

Hooniversity: [https://hooniversity.org/](https://hooniversity.org/)

Hoon School: [https://hooniversity.org/enroll/](https://hooniversity.org/enroll/)

Urbit / Hoon Docs: [https://urbit.org/docs/reference/](https://urbit.org/docs/reference/)

Buy a planet: 
- [https://urbit.live/](https://urbit.live/)
- [https://urbit.me/](https://urbit.me/)

Catch a comet: [https://urbit.org/docs/glossary/comet/](https://urbit.org/docs/glossary/comet/)

Tlon: [https://tlon.io/](https://tlon.io/)

Once you get on Urbit, join:

~bitbet-bolbel/urbit-community

~hiddev-dannut/new-hooniverse
