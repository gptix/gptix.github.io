---
layout: post
title: Sigmoid in Hoon
subtitle: Some Data Science
---

## *'The'* Sigmoid Function

A standard function in data science is the sigmoid function: 

**`sigmoid(z) = 1 / (1 + e^-z)`**`.

This function will:
- as **z** approaches infinity, asymptotically approach **1**;
- as **z** approaches negative infinity, approach **0**; and
- be **0.5** if **z** is *0*.

I believe any number can stand in the place of **e** in the formula for this function, and the three results above will be enjoyed. However, the smaller that number, the more slowly the result will approach limits.

## Hoon Code

# I found a bug.  Do not use this code in Production.

The steps of including code from other files, and calling gates from included code, is correct.

The problem seems to be in exp:lazytrig.  It seems to work for negative integers from -1 to -9, but hangs with -10.

I'm looking into it.

FWIW.

```
/+  lazytrig  :: From ~lagrev-nocfep, https://github.com/sigilante/lazytrig
|%
++  e-to-the
  :: Helper function to keep final function neater.
  |=  x=@rs  ^-  @rs
  (pow:lazytrig e:lazytrig x)

++  neg
  :: Helper function to keep the final function neater.
  |=  x=@rs
  (mul:rs .-1 x)

++  sigmoid
  :: 1 / (1 + e^-z)
  :: z large neg, approaches 0
  :: z == 0, 0.5
  :: z large pos, approaches 1
  |=  z=@rs  ^-  @rs
  (div:rs .1 (add:rs .1 (e-to-the (neg z))))
--
```

## Using the Code

To use the code from **dojo**

###  Boot a fake planet.

I'd be daft to risk my home planet on sketchy code.

`bash $ ./urbit zod`

(a lot of line melody)

`~zod:dojo> `

### Save code in your **pier**

Save **lazytrig.hoon** (created by **~lagrev-nocfep**, and available at [https://github.com/sigilante/lazytrig](https://github.com/sigilante/lazytrig)) in the **/lib/** directory of your pier.

Save the code above in some **foo.hoon** file, also in **/lib/**.

In **dojo**:

```
~zod:dojo>  |commit %home :: load your new code from your pier into your ship.
>=
: /~zod/home/1.869/lib/lazytrig/hoon
: /~zod/home/1.869/lib/foo/hoon
```

*Note*: The `1.869` will probably be different.  I believe it is an event counter.

### Get the code into your dojo.

```
~zod:dojo> =dojofoo -build-file %/lib/sigmoid/hoon
```
The response should be:
```
> =dojofoo -build-file %/lib/sigmoid/hoon
```

### Test
```
> =dojofoo -build-file %/lib/sigmoid/hoon
> (sigmoid:dojofoo .-9000000000)
.5.693553e-38
> (sigmoid:dojofoo .9000000000)
.8.5067096e-38
> (sigmoid:dojofoo .0)
.5e-1
```

**Success!**

## I've enjoyed my time here!

You all have been so wonderful!

It's never to soon to start learning Hoon!


See you on Mars!

**~habnus-dovres**

---

I suggest taking the in-person (and archived) class: *Beginning Hoon* or *Hoon 101*.

[https://hooniversity.org/enroll/](https://hooniversity.org/enroll/)

Hoon is a functional, typed language. Using Hoon, we can write **gates** that can run directly on **Arvo**, the **Urbit** OS.

## Hoon School Teaches Many Things

- How to write and use gates
- Some data types
- Recursion
- More

---
## Maybe of interest:

My code: [https://github.com/gptix/hoon/tree/master/libs](https://github.com/gptix/hoon/tree/master/libs)

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
