# Statistics Concepts used in ML
## Standard Deviation
- Describes how spread out the values are from the mean of data
- Represented by sigma
- The smaller the value the lesser the span of the data
- Square root of variance
- Can be directly used from numpy
  ```python
  import numpy
  speed = [86,87,88,86,87,85,86]
  x = numpy.std(speed)
  print(x)
## Variance
- Indicates how spread out the values are
- Represented by sigma square
- Can be directly used from numpy
  ```python
  import numpy
  speed = [32,111,138,28,59,77,97]
  x = numpy.var(speed)
  print(X)
## Standard Deviation vs Variance
- Variance is more calculation friendly as squaring makes it easier to work with values. So, standard deviation is mainly used for interpretation and variance is used for computation
- Many formulas are simpler when used with variance like ANOVA, regression, etc.
- Variance adds linearly: Var(X + Y) = Var(X) + Var(Y). There is no such rule for standard deviation
## Percentiles
- A number that describes the value that a given percent of values are lower than
- Can be directly used from numpy
  ```python
  import numpy
  ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]
  x = numpy.percentile(ages, 90)
  print(x)
