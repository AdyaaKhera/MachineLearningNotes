# Theory
## Statistics
### Standard Deviation
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
### Variance
- Indicates how spread out the values are
- Represented by sigma square
- Can be directly used from numpy
  ```python
  import numpy
  speed = [32,111,138,28,59,77,97]
  x = numpy.var(speed)
  print(X)
### Standard Deviation vs Variance
- Variance is more calculation friendly as squaring makes it easier to work with values. So, standard deviation is mainly used for interpretation and variance is used for computation
- Many formulas are simpler when used with variance like ANOVA, regression, etc.
- Variance adds linearly: Var(X + Y) = Var(X) + Var(Y). There is no such rule for standard deviation
### Percentiles
- A number that describes the value that a given percent of values are lower than
- Can be directly used from numpy
  ```python
  import numpy
  ages = [5,31,43,48,50,41,7,11,15,39,80,82,32,2,8,6,25,36,27,61,31]
  x = numpy.percentile(ages, 90)
  print(x)
### Normal Data Distribution
- Data where the values are concentrated around a given value
- Also known as **Gaussian data distribution**
- A normal distribution graph is also known as the **bell curve**
- (Do graphical shifts in curve wrt standard deviation and mean) - UCL course
### Linear Regression
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
### Polynomial Regression
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
### Multiple Regression
- Contains more than one independent value so the prediction is based on two or more variables unlike linear or polynomial regression where x was the only independent variable predicting the y's
- In multiple regression we use normal linear model from sklearn or other module but use all independent and dependent variables together at once for example, like a data frame object
  ```python
  X = [["A","B"]]
  y = ["C"]
## Scaling
Changing data into comparable values
### Standardization
- z = (x - u) / s
- Where z is the new value, x is the original value, u is the mean and s is the standard deviation.
- sklearn modeule has a method StandardScaler() for standardization
## Evaluation 
- Train/Test method
- 80% data for training and 20% data for testing
## Decision Tree
- A flowchart that helps makes decisions based on previous experience
- Feature columns are the columns we try to predict FROM in our dataset and the target columns are the ones we are trying to predict
- Always separate feature and target columns into X and y
  ```python
  from sklearn.tree import DecisionTreeClassifier
  dtree = DecisionTreeClassifier()
  dtree = dtree.fit(X,y)
  tree.plot_tree(dtree, feature_names=features)
- *gini* refers to the quality of split ranging from 0.0 to 0.5 where 0.5 means the split is done exactly in the middle and 0.0 means all samples got the same result
  - Gini = 1 - (x/n)^2 - (y/n)^2
  - x is positive answers, y is negative answers and n is the number of samples
- *samples* tell the number of data points that are yet to be sorted by the decision tree at a particular node / leaf
- *value* tells their split distribution based on the decision made
- **Decision tree won't give the same answer everytime because it selects features to make decisions on randomly even though its decisions are based on statistical information**
## Confusion Matrix
- Table used in classification problems to assess where errors were made
- rows represent the outcomes and the columns represent the predictions
  ```python
  from sklearn import metrics
  confusion_matrix = metrics.confusion_matrix(actual, predicted)
  display = metrics.ConfusionMatrixDisplay(confusion_matrix = confusion_matrix, display_labels = [0, 1])
  import matplotlib.pyplot as plt
  display.plot()
  plt.show()
- Since it has only two labels it creates a 2x2 matrix with four quadrants, True negative (results matched TRUE, both were zero NEGATIVE), False positive (results didn't match FALSE, the model predicted a one POSITIVE), False negative (results didn't match FALSE, the model predicted a zero NEGATIVE) and True positive (results matched TRUE, both were one POSITIVE)
### Accuracy
- measures how often the model is correct
- both true values / total values
- (TP + TN) / (TP + TN + FP + FN)
  ```python
  Accuracy = metrics.accuracy_score(actual, predicted)
### Precision
- measures the truly positive percentage out of all the predicted positives
- truly positive / all positives
- TP / (TP + FP)
  ```python
  Precision = metrics.precision_score(actual, predicted)
### Recall / Sensitivity
- out of all that should be positive what percentage is actually predicted positive is measured by recall
- correctly predicted positive / values that should be positive
- TP / (TP + FN)
  ```python
  Sensitivity_recall = metrics.recall_score(actual, predicted)
### Specificity 
- measures how well the model predicts negative results
- correctly predicted negative / values that should be negative
- TN / (TN + FP)
- In the code block below we are changing the positive label to 0 which means TN become TP and so on and then we calculate recall
  ```python
  Specificity = metrics.recall_score(actual, predicted, pos_label=0)
### F-Score
- harmonic mean of recision and recall
- 2 * ((precision * recall) / (precision + recall))
  ```python
  F1_score = metrics.f1_score(actual, predicted)


