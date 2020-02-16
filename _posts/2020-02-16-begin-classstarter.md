---
layout: post
title: classStarter
subtitle: A test project in Common Lisp
---

I really like Common Lisp, but I am only a hobby coder. I will create a project to learn and practice techniques and patterns for creating projects in Common Lisp.

# classStarter What Is

classStarter will be an auction system for a market of seats at classes at my hackerspace, [Freeside Atlanta](https://www.freesideatlanta.org/).

## classStarter Where

[classStarter, Like Kickstarter, but not for Kicks](https://github.com/gptix/classstarter)

## Approach

I will study and use techniques learned online, particularly following the [Atlanta Functional Programming Meetup](https://www.meetup.com/Atlanta-Functional-Programming-Meetup/) resources, currently available on Youtube at the
[Atlanta Functional Programming](https://www.youtube.com/channel/UCYg6qFXDE5SGT_YXhuJPU0A/videos) channel.

### Thoughts on design

What are the things?

Qvo Qvod?

Initially I'll use techniques described in [Practical Common Lisp](https://www.amazon.com/Practical-Common-Experts-Programming-Languages/dp/1430242906/), building and manipulating structures from lists.

I'll soon shift to using an SQL database, then probably use an ORM.

[Eitaro Fukamachi](https://github.com/fukamachi/) has made GREAT tools.


### Entities

- Person
  - Name
  - Role
  - email address
  - phone number
  - paypal address
- Role
  - Instructor
  - Attendee
  - Administrator
- Event (not a specific occurence)
  - Description
  - Materials
  - Equipment
  - Pre-requisites
  - Time constraints
- Occurence
  - Event definition ID
  - Venue
  - Start
  - Stop
  - Attendee Max
  - Min fee
  - Min revenue
- Bid (for seat(s) at an Occurence)
  - Occurence ID
  - Attendee ID
  - Seat Count
  - Bid per seat 
