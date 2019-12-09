---
layout: post
title: Meta with Hy and Python
subtitle: Meta Makes it Betta!
---

# Hy, Python, Data Science, and Meta-programming

**Hy** is an interesting language that can be used by Pythonistas to simplify work in data science.

## Why Hy?
Hy supports coding in a Lisp-y **(don't be scared!)** syntax, and Hy produces real python code.

Hy can be used to simplify use of common patterns. In particular, the Lisp-y syntax available in Hy, and, in particular, **Hy's ability to define Lisp-style macros**, allow that-which-is-always-the-same (boilerplate) to be coded once, and that-which-might-change (variations) to be used as parametric values.

## Getting Hy

Here is where to get Hy: http://docs.hylang.org/en/stable/quickstart.html

Python is heavily used in **data science** work. Python has a healthy related ecosystem. Great **libraries** include Numpy, Pandas, MatPlotLib, and Seaborn. Key **tools** are Jupyter notebooks, and Google's Colab notebooks. 

Hy can be used to generate Python code to glue these great tools together.

## Hy and Data Science

Here is a good article on how Hy can be used with Pandas: https://xvrdm.github.io/2017/10/26/getting-hy-with-pandas/

Pipelining is a great pattern for high-level control of sets of tasks that are often executed, and in a particular order. An example is:
Ingest data
Remove useless rows
Replace "not a number" values
One-hot encode categorical values
And so on.

**Pipelining** often involves chaining functions or procedures together so that output of one step becomes input to a following step. Intermediate steps are often defined to take, as input, one value (even if it is a huge, complex value, like a dataframe) and produce, as output one (even if...) value.

Hy has **a great tool** (the **threading macro**, written **->**) that allows these steps to be chained. However, if intermediate steps require multiple values as input, a chain cannot be continued.

The article above shows a way of dealing with this, inevitably breaking a chain of processing in twain.

## Hy and Metaprogramming

I want to **show how Hy's support of metaprogramming** supports unifying these two chains.
