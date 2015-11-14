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

# Documentation Warm-Up (50)
*Question*:  What is a library?

Let's warm-up our documentation comprehension skills by taking a look at the `random` library.

With a partner,
0. Google "python random"
1. Open up the official Python documentation of the `random` library.
2. Read about the `randint` function. What does it do?
3. Look up an example of it
4. Use it to generate a random number between 1 and 1000.

# Pandas (65)
*Question* What is [`pandas`](http://pandas.pydata.org/pandas-docs/stable/)?

[Here](https://s3.amazonaws.com/python-level-2/sales-funnel.csv) is our first data set.

## Preliminary Exercise
With your partner
0. Download and open the dataset
1. What is this dataset about?
2. What are some questions you might ask about the data?
3. Google/use the pandas documentation to read in a csv file from a URL.

## Basic Manipulation (75)
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

## Solo Practice (150)
0. Read in this dataset
1. What is this dataset about?
2. What is the average trip time?
3. What is the average trip time by station?

** STRETCH/BIO BREAK*

# Intro the Data Science (180)
*Think/Pair/Share*: What is data science? What are some examples of datascience

[Here](https://archive.ics.uci.edu/ml/machine-learning-databases/housing/housing.data) is our data set.
[Here](https://archive.ics.uci.edu/ml/machine-learning-databases/housing/housing.names) is the description of the data.

## Data Science Terminology
- features
- target

Examples:
- spam
- netflix

With a partner,
0. Read the data description
1. Discuss the data and what we could use this data for
2. Read in the data

Together, (190)
1. Let's assign the column names for ease of analysis.
2. Let's use pandas's built-in descriptive statistics method to get a statistical summary of the data.
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
2. Let's fit the linear regression model using 3 columns.
3. Let's plot the linear regression model.
4. Let's plot the predictions.
5. Let's measure the accuracy.
6. Let's see which columns were most predictive.
7. Let's use `cross_val_predict` as a shortcut.

On your own, (230)
0. Run the regression using all of the feature columns.
1. Use intercept. How does the model improve/worsen?
2. Plot the predictions against the true values.


# Using Data Science for Classification
## Even More Data Science Terminology
- regression
- classification

## Popular Classification Algorithms
- k Nearest Neighbors
- RandomForest
- Logistic Regression (poorly named, I know!)
- Support Vector Machines
- Neural Networks (Deep Learning...)

[Here's](https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/wdbc.names) a description of our dataset.
[Here's](https://archive.ics.uci.edu/ml/machine-learning-databases/breast-cancer-wisconsin/wdbc.data) the dataset.

By yourself, take 5 minutes to do the following:
0. Read the dataset description
1. Read the dataset into pandas

Together,
0. Separate into feature and target
1. Split into test and training set
2. Train the RandomForest and then test it out on the validation set. How did it do? Which features were most predictive?
3. Use cross_val_score instead as a shortcut for the above
4. Let's look at the documentation of the RandomForest

## Tuning the model
- Every data science model (algorithm) has parameters you can tune to improve the accuracy of the model.
- For RandomForest, what are the parameters we can tune? One is the number of trees in the forest.

5. Try out RandomForest with the following values of n_estimators: 5, 10, 20, 50, 100, 500
6. Plot the accuracies against the value of n_estimators.

# Saving and Sharing our Notebook
0. Download your notebook
1. Open it up in a text editor
2. Copy all the text
3. Paste it into a [gist][http://gist.github.com]
4. Create a secret gist
5. Copy the browser url
6. Go [here](http://ipython.nbviewer.org) and paste that url
7. Voila!

# Possible Next Steps
- Build a Django app
- Run through more pandas tutorials
- Run through some sci-kit learn tutorials and examples
- Go through some of [these iPython notebooks]()
- Take the GA Data Science [part time course]()
- To up your pure Python fluency, do tons of [Euler problems]()