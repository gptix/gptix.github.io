---
layout: post
title: Why I Like Urbit
subtitle: It's Never Too Soon
---

## I like coding.

I particularly like Lisp.  I also like Haskell a lot.

I like what the Internet could be. 

Unfortunately, now, the Internet is dominated by companies that require accounts, demand license to your data, throttle and **guide** interaction, and can and do deny service based on suspicious and opaque rules.

## Urbit is very different.

To use Urbit, one needs an identity (they come in **planets**, **comets**, **stars**, **galaxies**, and, for temporary use **comets**).

Each planet identity is an address on the Urbit network.  Planets must be purchased.  They cost roughly $20. Critically, purchases of planets are documented on a block chain (at present, Ethereum's). This makes your planet your property. It cannot be cancelled, although it can be ignored, if you are unpleasant.

The Urbit operating system is **Arvo**.  It is written in **Hoon**, a functional, typed language. Hoon has at its heart **Nock**, which is similar to **eval** in Lisps.

## Hey, Try it Out!
Learning Hoon is enjoyable and rewarding, and can be used to make real applications that run on your planet, and across the Hooniverse, such as via the Web interface **Landscape**.

Exploring Urbit and the Hooniverse is like blueshifting your conventional take. You will learn of **gates**, **wings**, **arms**, **legs**, **faces**, **tapes**, **cords** and **runes**. You will learn to pronounce **$** as **buc**, and **\|=** as **bartis** and **^-** as **kethep** and **@p** as **pat P**.  For good reasons.

- You will meet great people.

- It's never to soon to start learning Hoon.

See you up on Mars.

**~habnus-dovres**


---

## A snippet of Hoon:

```
++  strip-leading-spaces 
|=  str=tape
^-  tape
|- 
?~  str 
  str 
?:  =(' ' i.str) 
  $(str t.str) 
`tape`str 
```

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




