# Objectives
Students will be able to
- write basic Python programs
- read the documentation for external libraries and use those libraries
- use the basic functionality of `pandas` for data analysis
- use `matplotlib` to visualize their data
- use `scikit-learn` to create predictive models
- use iPython notebook to conduct their data analysis

# Agenda
0. Set up programming environment
1. Quick Review of Basic Python
2. Using Other Libraries
3. Intro to Pandas
4. Intro to Matplotlib
5. Wrap up & Closing thoughts

# Set Up Programming Environment (10)
## Download and Installation
Go through these steps on your own computer, but do so in collaboration with your neighbor.

0. Download and install anaconda (before class) [here](http://continuum.io/downloads).
1. Open Terminal
2. Run this command to create our development environment: `conda create -n pds pandas matplotlib ipython ipython-notebook scikit-learn` (This may take a few minutes)
3. Run this command to activate that environment: `source activate pds`
4. Run this command to open iPython notebook: `ipython notebook`

### Exercise: Getting Familiar with iPython Notebook
Run the following code in iPython notebook by typing it into a cell and pressing either the Play button or Shift+Enter to execute.

```python
print "Hello"
```

# Review of Basic Python (20)
## The Basic Data Types
What are the basic data types?
- Integers, e.g. 1, 2, 3
- Floating point numbers, e.g 2.3, 3.7
- String, e.g. "John Krasinski"
- bool, True or False
- None, which just corresponds to empty or null, if you've used other languages

## Variables
Now let's talk variables. What's a variable? It's a placeholder for a value.
```python
>>> x = 5
>>> y = 2
>>> x + y
7
>>> x = 3
>>> x + y
5
```

Note: there are rules for valid variable names, e.g. no spaces, no hyphens.

### Exercise
Do this exercise solo.

Set a variable called `age` equal to your age. Then create a new variable called `future_age` that you set equal to `age` + 10. Then print `age` and separately print `future_age`.

## Lists (30)
Lists is a super useful data type.
It's an ordered collection of items, which you can modify by adding or removing elements.

Let's learn the syntax of a list:
```python
>>> x = [1, 2, 3, 4, 5]
>>> len(x)
5
>>> # what's between the brackets is called the index
>>> x[0]
1
>>> x[1]
2
>>> x[4]
5
>>> x[6]
IndexError
>>> x.append("hello")
>>> len(x)
6
>>> x[5]
"Hello"
>>> # can remove elements, defaults to popping off the last one
>>> x.pop()
>>> print x
>>> # can specify the index
>> x.pop(2)
>>> print x
>>> # can do a boolean check if something is in the list
>>> 5 in x
False
>>> 1 in x
```

### Exercise
```
- Create a list called `restaurants` consisting of the following elements in this order:
"Laut", "Random String", "Chipotle", "Eataly", "Sophie's Cuban", "Chop't", "Potbelly's"
- Get the third element of the list
- Add "Ootoya" to the end of the list
- Use .pop() to remove "Random String" from the list
- Print the list
- Check if 'Chipotle' is in the list
- Check if 'Random String' is in the list
- Get the length of the list
```

## Dictionaries (50)
Dictionaries are also massively useful. You can think of them as maps, between as set of keys and their corresponding values.
Let's look at one in the shell to better understand how they work and how they can be useful:

```python
>>> # Here's the syntax, {} with key:value, with key being a string.
>>> person = {"name": "John Jameson", "age": 31, "hobbies": ["tennis", "python", "piano"]}
>>> person["name"]
>>> # like a string, we use the brackets but instead of the index, we provide the key name
>>> person["age"]
>>> hobbies = person["hobbies"]
>>> len(hobbies)
>>> hobbies[1]
>>> person["random"]
KeyError
>>> person["location"] = "New York"
>>> person["deepest_darkest_secret"] = "Loves Vampire Diaries"
print person
>>> del person["deepest_darkest_secret"]
print person
>>> person.keys()
>>> person.values()
>>> person.items()
>>> # check if a key exists in the dictionary
>>> "name" in person
>>> "secret" in person
```
### Exercise
```
Create a dictionary called `class_data` with the following keys:
- "course_name", which should correspond to "Intro to Python"
- "student_count", which should correspond to number of students, say 20
- "instructor", which should itself be a dictionary with the following keys
    - "name" ("Suneel")
    - "gender" ("M")
    - "can_program" (True)
- get the student count from the dictionary
- get the instructor name from the dictionary
```

## Loops (90)
Loops let us pass through a set of values and do some operation on each.
There are different kinds of loops, for loops and while loops. They're quite similar, but let's look at the canonical loop, the for loop.

### The modulo function
```python
>>> 4 % 2
>>> 5 % 2
>>> 6 % 2
>>> 7 % 2
>>> 10 % 5
>>> 11 % 5
```

What's happening here?

### For loop example

```python
>>> numbers = [1, 2, 8, 7, 9, 10]
>>> odds = []
>>> for dog in numbers:
        if dog % 2 == 1:
            odds.append(dog)

print odds
```
- the `dog` in the for loop syntax is a dummy variable that refers to the element in the list that we're passing through. The first time around, `dog` refers to 1, the last time it refers to 10.
- we are going through this list and if the number is odd, we add it to the odds list that we initialized before the for loop.

### A useful function: `range`
Before we move on to some practice problems, here is a useful function:
```python
>>> range(10)
```

### Exercise
- Construct a list of numbers between 0 and 1000 that are divisible by 33

## Functions (120)
Functions are the heart and soul of python. Functions are blocks of code that take an input and based on some rules produce an output.

Let's learn the syntax of functions:

```python
>>> def add(a, b):
        return a + b
>>> z = add(3, 4)
>>> print z
```
a and b are variables that the function `add` takes

### Exercises
- solo: create function `multiply` that takes two variables and returns their product
- with a partner: write a function that takes a list of numbers and return True if the sum of the numbers is even and False otherwise.

# Using Other Libraries (150)
What is a library? A reusable, collection of code that someone else (or you) has already written. Some great built-in libraries:
- `random`
- `csv`
- `collections`
- `datetime`

To use other libraries, we need to be able to:
- understand the documentation of that library
- understand what the inputs and outputs of their functions are
- how to call those functions correctly

Let's start with the random library.

## The `random` library.
Our first step is to locate the documentation. Google "python random". It should take you [here](https://docs.python.org/2/library/random.html)

Let's import the library
```python
>>> import random
>>> dir(random)
```

How does python know what `random` is and how to find the code? Because it comes built-in to the Python language. Other libraries such as `pandas` will have to be installed prior to use.

### Exercises
1. Find the `randint` function in the documentation and explain to your neighbor what it does and how to use it.
2. Again, with your partner, use the `randint` function to generate a random number between 1 and 125.


## What is `as`?
```python
>>> import random as rd
```

Let's see what happens...

# Intro to Pandas (175)
What is [pandas](http://pandas.pydata.org/pandas-docs/stable/)?

- analyze tabular data
- built on top of `scipy` and `numpy`, so quite fast and it's good to know some of the basics of those libraries as well since you'll likely use some function calls and have to interact with numpy arrays which are fancy, scalable lists.
- incredibly powerful

## Our First DataSet
[Here](https://s3.amazonaws.com/python-level-2/sales-funnel.csv) is the data set.

### Exercise
With your partner, download the data and look at it in excel.

Questions:
- What is this dataset about?
- What are some questions you might ask about the data?

### Importing pandas
```python
>>> import pandas as pd
```

### Exercise (185)
We want to read in the csv file. With your partner, look in the pandas documentation (or Google) to find out how to read in a csv file given a URL.
Then, read in the csv file from the above URL.

*Note*: We're going to be heavily commenting our code so that each step is super clear and we can refer back to it in the future and immediately understand what's being done.

### Basic manipulation
```python
# We've already read in csv data and saved it to a DataFrame called df
# Let's see the columns
>>> df.columns
# Let's only see the first 5 rows
>>> df[:5]
# Let's only look at Name and Status
>>> df[["Name", "Status"]]
# Let's look at just Name
>>> df["Name"]
```
### DataFrame vs DataSeries
```python
>>> type(df)
>>> df["Name"]
# just pass in the string "Name" in brackets
# and we get a Series (1-dimensional)
>>> type(df["Name"])
# instead if you pass in the list ["Name"] in the brackets
# we get a 2-dimensional DataFrame
>>> type(df[["Name"]])
```

### Questions (200)

#### Filtering dataframes
Let's learn how to filter the data according to some criterion.
- How many accounts have been won?

```python
>>> df[df['Status'] == 'won']
```

Exercise:
- Solo: How many accounts have a price greater than $12,000?

#### Getting the max value (and similar quantities) (210)
What is the maximum account price?

Exercise:
- Solo: What is the minimum account price?
- Solo: What is the mean account price?
- Solo: What is the sum of all the prices?


#### Aggregating (220)
- What is the total dollar amount pending?

Steps:
1. add a column called Amount that is Quantity times Price
2. select the subtable where status is pending
3. sum up the filtered amounts in that subtable


#### Pivot table basics (230)
Pivot tables are a great tool to summarize the dataset. Same concept as in Excel. Let's try it out

First, let's take a look at the documentation [here](http://pandas.pydata.org/pandas-docs/stable/generated/pandas.pivot_table.html).

```python
>>> pd.pivot_table(df, index=["Name"])
>>> pd.pivot_table(df,index=["Manager","Rep"])
>>> pd.pivot_table(df,index=["Manager","Rep"],values=["Price"])
# Is the price column correct?
# import the numpy library to us the sum function
>>> import numpy as np
>>> pd.pivot_table(df,index=["Manager","Rep"],values=["Price"],aggfunc=np.sum)
```
Exercise:
- With partner: create a pivot table that indexes on Manager and Status and displays only the column Price, which contains the total price of accounts for each (Manager, Status) pair.
- Solo: create a pivot table indexing on Status and displays only the column Price summed up per status.

# Plotting with `matplotlib` (240)
Let's write this in the notebook:
```python
>>> %pylab inline
```
This specifies that plotted figures will be displayed in the notebook directly.

## Try this
```python
import pylab
import numpy as np


x = np.linspace(0, 20, 1000)  # 100 evenly-spaced values from 0 to 50
y = np.sin(x)

pylab.plot(x, y)
```
What do you see?


## Customizing axes and titles
```python
pylab.plot(x, y)

pylab.xlabel('this is x!')
pylab.ylabel('this is y!')
pylab.title('My First Plot')
```

## Two plots together, with a legend
```python
x = np.linspace(0, 20, 1000)
y1 = np.sin(x)
y2 = np.cos(x)

pylab.plot(x, y1, '-b', label='sine')
pylab.plot(x, y2, '-r', label='cosine')
pylab.legend(loc='upper right')
pylab.ylim(-1.5, 2.0)
```

## Exercise
```
x = [1, 2, 3, 4, 5]
y = [2.3, 4.5, -5.6, 7.8]

Plot x against y.
```

# Real Data Science (260)
We're going to apply multivariate linear regression on the data to create a model that predicts house price based on other factors.

## Question
- What is linear regression?
- What is a data science model?
- What is cross-validation?

## Code
The `scikit-learn` library is a goldmine of standard statistical and machine learning algorithms.

[Documentation](http://scikit-learn.org/stable/documentation.html)

We are going to step through an example of predicting Boston house prices using linear regression.

# Next Steps
Some recommendations as you move forward:
- build a Django app
- do more Pandas data analysis
- build d3.js data visualizations
- use scikit-learn to do machine learning
- take the GA Data Science part-time course

# Sources
- [Pivot Tables Explained](http://pbpython.com/pandas-pivot-table-explained.html)
- [Plotting Tutorial](http://jakevdp.github.io/mpl_tutorial/tutorial_pages/tut1.html)
- [Linear Regression on Boston Housing Data](http://scikit-learn.org/stable/auto_examples/plot_cv_predict.html#example-plot-cv-predict-py)
- [Class-specific notebook on scikit-learn](http://nbviewer.ipython.org/gist/suneel0101/d5b521a7d300b0e58325)