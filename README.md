# Objectives
Students will walk away with introductory & practical knowledge of the Python Data Science stack:
- pandas
- matplotlib
- scikit-learn

# Setup
1. Go to [tmpnb.org](http://tmpnb.org).
2. Select `New` > `Python 2` to create a Python notebook.
2. Follow along with me:

```python
>>> import pandas
>>> import sklearn
>>> import matplotlib
```

# Agenda
0. Python Warm Up
1. Intro to Pandas
2. Intro to Data Science with Sci-kit Learn
3. Visualization with Matplotlib
4. More Practice

# Python Warm-Up / Review (20)
This problem will give us a review of lists, for loops and lambda functions

Given the following list,

```
names = ["Michael Fassbender", "Karlie Kloss", "Taylor Swift", "Justin Bieber"]

```
1. print out the names that contain the letter "l"
2. turn all of the names lowercase
3. sort the list of names alphabetically using the built-in `sorted` function (HINT: Use Google)
4. sort the list of names by length using the built-in `sorted` function

# Pandas (65)
*Question* What is [`pandas`](http://pandas.pydata.org/pandas-docs/stable/)?

[Here](https://s3.amazonaws.com/python-level-2/sales-funnel.csv) is our first data set. Let's download it and upload it to the datasets folder within the notebook.

## Preliminary Exercise
With your partner
0. Download and open the dataset
1. What is this dataset about?
2. What are some questions you might ask about the data?

## Basic Manipulation (75)
0. Let's read in the data.
0. How do we see what columns are available?
1. How do we look at just the head or tail of the dataset?
2. How do we look at only a few rows?
3. How do we only look at certain columns?
4. How do we pull out a column and look at it as a series?

## Filtering DataFrames (80)
0. How do we look at only those rows that have Status = won
1. Exercise: How many accounts have a price greater than $12,000?
2. How do we get the maximum value of a certain column?
3. Exercise: What is the minimum account price? The mean? The sum? The standard deviation?

**LUNCH**

## Aggregating data (120)
What is the total dollar amount pending?

0. How do we add columns?
1. Let's add a column called Amount that is equal to Quantity * Price
2. Exercise: Let's select just those rows where status is pending and sum up those amounts.

## Pivot tables (130)
*Question*: What are pivot tables? Why are they useful?

Let's take a look at the documentation [here](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.pivot_table.html).

0. Let's pivot using one index.
1. Let's pivot on multiple indexes
2. Let's reverse those indexes
3. Let's specify which values we care about
4. Let's specify which columns we want broken down
5. Let's specify how we want the values to be aggregated (`aggfunc`)
6. Let's fill N/A values
7. Let's get subtotals

(Creative) Exercise: with a partner, use pivot tables to play around with the data. What pivots do you find particularly interesting or useful for this dataset?

## (Depending on Time) Solo Practice (150)
0. Read in [this dataset](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/citibike-data-truncated.csv)
1. What is this dataset about?
2. Let's delete the Unnamed: 0 column.
4. Let's compute the duration by turning starttime and stopttime into datetime objects and computing their difference.
5. What is the average trip time? What is the minimum and maximum trip time? What is the standard deviation?
6. What is the average trip time by station? (Hint: Use pivot tables)

**STRETCH/BIO BREAK**

# Intro the Data Science (180)
*Think/Pair/Share*: What is data science? What are some examples of datascience

- [Here](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/Boston_Housing.csv) is our data set.
- [Here](https://archive.ics.uci.edu/ml/machine-learning-databases/housing/housing.names) is the description of the data.

https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/housing_prices.csv

## Data Science Terminology
- features
- target

Examples:
- spam
- netflix

With a partner,

0. Read the data description
1. Discuss the data and what we could use this data for
2. Upload to datasets/ in the notebook and read in the data with pandas.

Together, (190)

1. Let's use pandas's built-in descriptive statistics method to get a statistical summary of the data.
3. Let's plot CRIM against MEDV
4. By yourself, generate the remaining 12 plots (ZN against MEDV, ..., LSTAT against MEV)
5. Which feature looks to be most predictive

*Think/Pair/Share*: What is linear regression? (It's machine learning!) (210)

## More Data Science Terminology
- cross validation
- training set
- validation set

Together, (215)

0. Let's separate the data into feature and target.
1. Let's separate the feature and target into training and validation set.
2. Let's fit the [linear regression model](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) using 3 columns.
3. Let's plot the linear regression model.
4. Let's plot the predictions.
5. Let's measure the accuracy.
6. Let's see which columns were most predictive.
7. Let's use [`cross_val_predict`](http://scikit-learn.org/stable/modules/generated/sklearn.cross_validation.cross_val_predict.html) as a shortcut to get the predicted values.
8. Let's use [`cross_val_score`](http://scikit-learn.org/stable/modules/generated/sklearn.cross_validation.cross_val_score.html) as a shortcut for the R^2 values. What does `cv` do?



On your own, (230)

0. Run the regression using all of the feature columns.
1. How does the model improve/worsen?


# Using Data Science for Classification (240)
## Even More Data Science Terminology
- regression
- classification
*Question*: What are some more examples of regression applications? classification applications?

## Popular Classification Algorithms (245)
- RandomForest
- Logistic Regression (poorly named, I know!)
- Support Vector Machines
- Neural Networks (Deep Learning...)
- k Nearest Neighbors

## Overview of K Nearest Neighbors (250)
- simple model
- works well when there aren't too many different features
- works well when the scale of each feature is similar (why?). we'll see this in our example.

### Worksheets (260)
- [kNN in one dimension](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/worksheets/worksheet_1_kNN.pdf)
- [kNN in multiple dimensions](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/worksheets/worksheet_2_kNN.pdf)

## Dataset (275)
- [Here's](https://s3-us-west-2.amazonaws.com/ga-dat-2015-suneel/datasets/breast-cancer.csv) a description of our dataset.
- [Here's](https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/wdbc.data) the dataset.


### Preliminary Exercises
By yourself, take 5 minutes to do the following:

0. Read the dataset description. What is this dataset about?
1. Upload the dataset to datasets/ in our notebook and read the dataset into pandas

### Together (280)

0. Separate into feature and target
1. Use cross val to run [`KNeighborsClassifier`](http://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
2. Plot these values of n_neighbors 2, 3, 4, 5, 10 against accuracy score. How did it do?
3. Let's describe the data.
4. Let's normalize the data using [`normalize`](http://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.normalize.html)
5. Try KNeighbors again for the different values of n_neighbors. How did it do? Which value of n_neighbors was best?
6. Let's manually use `train_test_split` and compare the predicted values with the true values in the test set to more concretely see the output of the model.

### Tuning the model
- Every data science model (algorithm) has parameters you can tune to improve the accuracy of the model.
- For kNN, what can/did we tune?


# Saving and Sharing our Notebook (310)
0. Download your notebook
1. Open it up in a text editor
2. Copy all the text
3. Paste it into a [gist](http://gist.github.com)
4. Create a secret gist
5. Copy the browser url
6. Go [here](http://nbviewer.ipython.org) and paste that url
7. Voila!

# Possible Next Steps
- Build a Django app
- Run through more pandas tutorials
- Run through some sci-kit learn tutorials and examples
- Take the GA Data Science part time course
- To up your pure Python fluency, do tons of [Euler problems](https://projecteuler.net/archives)