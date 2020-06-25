---
layout: page
title: A Simple DecisionTree Classifier
subtitle: Python, no Numpy, No Pandas, No Scikit
---

# My DecisionTree class

A **DecisionTree** is a Python class that be instantiated to
- hold information about a set of observations,
- construct a hierarchy of tests and sets of observed 'features'
- use that hierarchy to use a new observation to 'predict' a feature value.

At the top level, I have implemented the class **DecisionTree**, and, for it, defined the methods **fit** and **predict**.

## How to use:

### The ```DecisionTree``` class

A DecisionTree is created by passing a 2D array to the constructor.
The rightmost column must be the 'feature' to be predicted.
The other columns must be the attributes whose values are used to predict the value of the 'feature'.

where **automobile_data** is an array:

```foo = DecisionTree(automobile_data)
```


Optionally, a list of column names can be passed via the parameter **colnames**.  No use of this is currently implemented.

```foo = DecisionTree(automobile_data, colnames = my_list_of_column_names)
```

### The ```fit()``` method of the DecisionTree class

The method **fit** does the work of taking a set of information about observations, measurements, attributes, and festures, and building a binary tree structure that can be used for later predictions.

Once an instance of DecisionTree exists, it can be fitted like so:

```
foo.fit()
```

### The ```predict()``` method of the DecisionTree class

The **predict** method is used to calculate, for one row of input data, the **classification** that the decision tree predicts for that input.

The row must have exactly one value for each attribute (input column) in the data used to fit the data tree classifier.

where **my_row_of_data** is 1D array of values, aand **foo** is a DecisionTree: 

```
foo.predict(my_row_of_data)
```

The value returned will be a Python dict, with key / value pairs with 
- the key being a possible class, and 
- the value being the count of 'copies' of that class found after following the path of questions embedded in the decision tree.

Simple case:

```
{'Apple': 1}
```

Less simple cases:

```
{'Apple': 13}
```

```
{'Apple': 13 , 'Peach': 2, 'Watermelon': 1}
```

## Explanation

### Terminology

- Data we will use is organized in **observations** (also called **records**, or **rows**).
- Each observation has one or more **attributes** (fields).
- Each attribute has a **value**.
- One attribute can be a **feature**, to be **predicted**.

For instance, we might use the attributes of a car we observe 
```
| attribute | value    |
|-----------+----------|
| color     | silver   |
| make      | Mercedes |
| model     | D2000    |
```
to predict a 'feature', such as 'purchase price'.

These are usually organized as rows within arrays, like

```
| color  | make     | model | price  |
|--------+----------+-------+--------|
| silver | Mercedes | D2000 | $75000 |
```

### Strategy

The strategy used by the fit method is to construct tests that can be applied to observations to determine a path through **DecisionNodes** in a tree to reach a **LeafNode**, where possible facts ("dog", 'vampire", "vanilla") are stored.

This process of constructing a tree is recursive, and therefor potentially very computationally expensive.

#### Base Case
To avoid unending computation, a recursive algorithm must include one (or more) base case.

Our fit algorithm will stop when 
- it receives no information to make a tree or subtree from, or 
- it can find no way to usefully divide 

This will occur if the data has only one row, or there is no way to separate the rows, like maybe 20 identical records.

To test this, we test every combination of attribute and value (these combinations are 'tests' or 'questions') and see how efficiently the combination separates remaining records into two smaller sets.

#### Gini Impurity

This is a measurement of the **purity** of relationships between attributes used to make predictions, and the features we would predict.

For instance, if we have one hundred apples, and one hundred predictions of 'apple', **IMPURITY** is zero.

Our tree-building algorithm should be designed to reduce impurity at each step.

Here is a link to an article I found useful: https://victorzhou.com/blog/gini-impurity/

#### Information Gain

This is another metric used to quantify the usefulness of a tested method of splitting a dataset into smaller sets.

This meaure is 'mathy', so i will not go into it in this article.

Here is a link to an article I found useful: https://victorzhou.com/blog/information-gain/


## The underlying binary tree

The DecisionTree is built using nodes arranged in a binary hierarchy.


### DecisionNode (class)

A Decision Node will hold a Tester, which is an instance of the Tester class, each of which indicates which column of a row a tester will test, and a value that will be used to discriminate 'true' from 'false'.

A DecisionNode will also hold one or two pointers to child nodes.

### LeafNode (class) 

A LeafNode will contain only a set of rows. These are the terminal nodes reached at the end of a path through DecisionNodes. The number and 'class' values of the rows in the LeafNode's set of rows can be used to report absolute counts, or used to calculate percentages, of classes returned.

### Tester (class)
An instance of this class holds *col* (an index to be used when testing a record), and *val* (a value to test the value in the record at that index).

Instances also have a method *passes*, which takes a record, and uses the instance's col and val to test the valuein the received record at the index.

### Important Helper Functions

#### ```distinct()```

This is used to return, for a set of rows, the distinct values that occur in one specified column.  This is used in calculation of Gini Impurity.

#### ``` tally()```

This is used to return a tally of the occurrences of each distinct value in a specified column of a set of rows.  This is also used in calculation of Gini Impurity.

#### ```gini_impurity()```

This calculates the Gini Impurity for a set of rows, considering the counts of distinct values of the 'class' for each row.

#### ``` information_gain()```

Roughly, the quantization of the reduction in entropy brought about by splitting a set of data in a certain way.

#### ``` best-split()```

A function that iterates over the set of all splits (gotten by splitting a set of records using a Tester). On each iteration, if the information gain is better than earler ones, the new, better one is stored. At the end, the best Tester, and the gain from its use, is returned.

This function is used to recursively build an efficient binary tree from rows of data.
 
