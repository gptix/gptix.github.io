#Hy, Python, Data Science, and Metaprogramming

Hy is an interesting language that can be used by Pythonistas to simplify work in data science.

Hy supports coding in a Lisp-y (don't be scared!) syntax, and Hy produces real python code.

Hy can be used to simplify use of common patterns. In particular, the Lisp-y syntax available in Hy, and, in particular, Hy's ability to define Lisp-style macros, allow that-which-is-always-the-same to be coded once, and that-which-might-change to be used as parmetric values.

Here is where to get Hy:

Python is heavily used in data science work. Python has a healthy related ecosystem. Great libraries include Numpy, Pandas, MatPlotLib, and Seaborn. Key tools is Jupyter notebooks, and Google's Colab notebooks. 

Hy can be used to generate Python code to glue these great tools together.

Here is a good article on how Hy can be used with Pandas:

Pipelining is a great pattern for high-level control of sets of tasks that are often executed, and in a particular order. An example is:
Ingest data
Remove useless rows
Replace "not a number" values
One-hot encode categorical values
And so on.

Pipelining often involves chaining functions or procedures together so that output of one step becomes input to a following step. Intermediate steps are often defined to take, as input, one value (even if it is a huge, complex value, like a dataframe) and produce, as output one (even if...) value.

Hy has a great operator that allows these steps to be chained. However, if intermediate steps require multiple values as input, a chain cannot be continued.

The arcticle above shows a way of dealing with this, inevitably breaking a chain of processing in twain.

I want to show how Hy's suppport of metaprogramming supports unifying these twwo chains.
