# Theory
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
## Normal Data Distribution
- Data where the values are concentrated around a given value
- Also known as **Gaussian data distribution**
- A normal distribution graph is also known as the **bell curve**
- (Do graphical shifts in curve wrt standard deviation and mean) - UCL course
## Linear Regression
- A line drawn to depict a relationship among data-points, mostly to predict future values
  ```python
  import matplotlib.pyplot as plt
  from scipy import stats
  x = [5,7,8,7,2,17,2,9,4,11,12,9,6]
  y = [99,86,87,88,111,86,103,87,94,78,77,85,86]
  slope, intercept, r, p, std_err = stats.linregress(x, y)
  def myfunc(x):
    return slope * x + intercept
  mymodel = list(map(myfunc, x))
  plt.scatter(x, y)
  plt.plot(x, mymodel)
  plt.show()
- The slope and intercept are used from the linear regression method to plot the line
- r here is the coefficient of relationship which ranges from -1 to 1 where 0 means no relationship
## Polynomial Regression
- Comes up with the best possible relationship to draw a line through data points, forming a non-linear shape
  ```python
  import numpy
  import matplotlib.pyplot as plt
  x = [1,2,3,5,6,7,8,9,10,12,13,14,15,16,18,19,21,22]
  y = [100,90,80,60,60,55,60,65,70,70,75,76,78,79,90,99,99,100]
  mymodel = numpy.poly1d(numpy.polyfit(x, y, 3))
  myline = numpy.linspace(1, 22, 100)
  plt.scatter(x, y)
  plt.plot(myline, mymodel(myline))
  plt.show()
- r squared measures the polynomialr egression relationship and it ranges from 0 to 1
  ```python
  print(r2_score(y, mymodel(x)))
## Multiple Regression






