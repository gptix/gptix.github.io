---
layout: page
title: Using PEP8
subtitle: Making your code better!
---

## Check Python Code for PEP8

[PEP8](https://www.python.org/dev/peps/pep-0008/) is a widely accepted set of coding conventions for Python code. Adherence to these conventions helps with retention of knowledge, and communication betweeen coders sharing responsibility for code.


Code can be checked for compliance with PEP8 in a number of ways:

## Online

[http://pep8online.com/checkresult](http://pep8online.com/checkresult)

## Using Local Code

[autopep8](https://pypi.org/project/autopep8/)

**autopep8** can be run from a command line to automatically refactor code to adhere to PEP8.

```$ pip install --upgrade autopep8```

Then something like

```$ autopep8 -v --in-place --aggressive --aggressive ~/ypurpath/somecode.py cd ~/gitstuff/lambdata```

can be used.
