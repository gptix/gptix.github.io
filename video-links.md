---
layout: page
title: Video Links
subtitle: Go straight to the dope
---

# Two Visualization tequniques for Models
- Partial Dependence Plots
PDP's help explain relation of individual features vs. model

- Shapley Value Plots
SHAP plots help explain individual predictions

Coefficients from linear models can be used to generate these.


[Intro]("https://youtu.be/5h8BWAPar0k?t=10")


# Links to cool points
[Partial Dependance Plots](https://youtu.be/5h8BWAPar0k?t=45)

PDP's can be used to relate one or two independant variables to the dependant variable. The limittion to two is only because visualization of more than three variables is hard.

What does a line plot of a PDP for one independant variable look like? 

[PDP line plot](https://youtu.be/5h8BWAPar0k?t=57)

What does a heat map of a PDP for two indepenedant varabviles look like? 

[PDP heat map](https://youtu.be/5h8BWAPar0k?t=481)

[Start of PDP code](https://youtu.be/5h8BWAPar0k?t=859)

[3D surface plot PDP](https://youtu.be/5h8BWAPar0k?t=992)


[Code](https://youtu.be/5h8BWAPar0k?t=1067)

[Code, Linear Regression and R^2 score](https://youtu.be/5h8BWAPar0k?t=1104)

[Linear Regression Coefficients](https://youtu.be/5h8BWAPar0k?t=1138)


Linear regression models will miss non-linearities.

[Gradient Boosting Model](https://youtu.be/5h8BWAPar0k?t=1486)

Gradient Boost models can better fit non-linearities, but then do not produce coefficioents.

[PDP purpose](https://youtu.be/5h8BWAPar0k?t=1522)

NB: Whether to use training data or validation data or combination is not currently decided.

[Explanatory animation](https://youtu.be/5h8BWAPar0k?t=1547)

On the animation, lines joining points of a color are ICE curves (Individual Conditional Expenctation).

[PDP with one feature](https://youtu.be/5h8BWAPar0k?t=1857)

- module pdpbox.pdp

- functions 
  - pdp\_isolate\_ and 
  - pdp_plot

[Instructions for Build Week](https://youtu.be/5h8BWAPar0k?t=2308)

