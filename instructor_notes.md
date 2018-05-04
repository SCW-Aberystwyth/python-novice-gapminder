# Instructor Notes - Plotting and Programming in Python

## Intro

* Introduce yourself
* Introduce helpers
* Fire exits, toilets
* explain what Software Carpentry is
* timetable for the day
* PC Logins
* Etherpad
* Code of Conduct
* Pre-workshop questionaire 
* Check Anaconda3/spyder installed on laptops

### Explain how session works 

* live coding
* Post stick notes
* quizes/exercises
* ask questions
* help each other

### Background to Python

* flexible language, lots of scientific use
* easy to learn the basics
* popular, lots of examples, books, help forums, jobs want it
* forces some best practice 
* less verbose than other languages 


## Running and Quitting

* Load spyder
* show anaconda navigator for those with own laptops
* make font bigger

* Explain code editor and console
* python vs ipython console
* files can be saved and run from the command line, useful on HPC
* change working directory in spyder, useful for this to be the same as data dir later to avoid long paths 

## Variables and Assignment

### Variables 

variables store values, text or number
= assigns from right to left

```age = 42```
```first_name = ahmed```

explain variable explorer
explain variable names can only be letters, digits and underscores. Cannot start with a digit
double underscore at the start has special meaning


### print

explain what print does
functions called by writing their name followed by brackets with arguments
strings must be in double or single quotes

```print(first_name,'is',age,'years old')```

explain variables must exist before they are used

```print(last_name)```

causes NameError

explain variables persisting across our console. Show closing the console to loose the state.

explain variable calculations, strings vs integers

(rerun script to bring back prior state)
```age = age + 3```
```print('Age in three years:',age)```

we get substrings using [x] where x is the index, starts from 0. error when it goes off the end

```atom_name = 'helium'```
```print(atom_name[0]``` 

explain slice notation [x:y] gets all characters from position x to y-1

```print(atom_name[0:3]```

len gets us string length. Functions can be nested, inner function evaluated first.

```print(len('helium'))```

explain variable names are case sensitive. Use meaningful variable names. Python doesn't care, humans do.

## Data Types and Type conversion

types are integers, floats and strings 
ints positive or negative whole numbers, floats positive or negative decimals, strings contain text. Text can include numbers.
type function tells you the type of something

```print(type(52))```

```fitness = 'average'```
```print(type(fitness))```

some operations can only work with certain types, e.g. maths on floats/ints only

```print(5-3)```
```print('hello' - 'h')```

+ operator has two meanings. Will add numbers or join strings.

```full_name = 'Ahmed' + ' ' + 'Walsh'```
```print(full_name)```

multiplying a string by an integer repeats the string

```separator = '=' * 10```

strings have a length, but numbers don't

```print(len(full_name))```
```print(len(52))```

strings can't be added to numbers
```print(1+'2')```

we can convert strings which contain digits to integers or floats

```print(1 + int('2'))```

or we can convert numbers to strings

```print(str(1) + '2')```

can mix integers and floats, conversion is automatic

```print('half is', 1 / 2.0)```
```print('three squared is', 3.0 ** 2)```

variables only change when assignment happens. There's no automatic update from prior operations. Those coming from only using Excel might have encountered this.

``` first = 1```
``` second = 5 * first```
``` first = 2```
``` print('first is',first,'second is',second)```

### Exercises
* fratctions
* automatic type conversion
* choosing types
* division types
* converting strings to numbers
* arithmetic with different types
* complex numbers

### Summary

* Every value has a type.
* Use type to find the type of a varaible
* Types control what operations can be done
* Strings can be added and multiplied.
* Strings have a length (but numbers don’t).
* Can convert numbers to strings
* integers and floats can freely mix
* Variables only change value when something is assigned to them

## Built in Functions and Help

Comments are any line starting with a #

Functions take zero or more arguments
we've seen len (1 arg), int/str/float (1 arg), print (zero or more) with none it prints blank line

```print('before')```
```print()```
```print('after')```

max finds largest value, min smallest, works on characters too

```print(max(1,2,3))```
```print(min('a','A','0'))```

some functions have default values for their arguments 
round will round to zero decimal places by default, but we can specify it

```round(3.712)```

rounds to 4

```rounds(3.712,1```

rounds to 3.7

help function gives us help on another function

```help(round)```

### Errors

syntax errors occur when python doesn't understand the program
```name='Feng```
```age = = 52```
```print("hello world"```

Runtime errors occur when something goes wrong while running the program

```age = 52```
```remaining = 100 -aege```

Every function returns something
Functions which have nothing to return give back None
```result=print('example')```
```print('result of print is',result)```

### Exercises

* understanding function order (remember BODMAS)
* spot the difference
* why not
* last character of a string

### Summary
* comments start with a #, only for humans
* functions take zero or more arguments
* built in functions include min, max, round and help
* functions only work for certain arguments, might have default values
* every function reutrns something, but it might just be None
* python gives syntax errors when it can't understand the code
* python reports runtime errors when something goes wrong running the code
* fix syntax errors by reading code, runtime errors harder need tracing what's happening

## Break time
* feedback no poststick notes, one positive one negative. Are we going too fast or slow?
* reflect on errors in python, did code always work as expected, how could you prevent errors in your code?

## Libraries

libraries are collections of functions that add additional funcionality. They can also contain data.
Python standard library comes with python and includes many useful things, date/time, random numbers, stats, file manipulation etc
Additional libraries available. Use import statement to load them (once they are installed). Anaconda installed a lot of useful libraries for us.

libraries must be imported before they can be used. 

```import math```
```print('pi is',math.pi)```
```print('cos(pi) is',math.cos(math.pi))```

have to reference the library with math. everytime we want something from it
help can tell us about a library

```help(math)```

we don't have to import the whole library, can just have certain functions. No need to use library prefix.
```from math import cos,pi```
```print('cos(pi) is',cos(pi))```

we can alias a library name for a shorthand. nice to shorten long names, needs to be unambigious still.
```import math as m```
```print('cos(pi) is',m.cos(m.pi))```

### Exercises
* exploring math module
* loading the right module
* jigsaw puzzle
* when is help availabe
* importing with aliases
* many ways to import
* importing specific items
* reading error messages

### Summary 

## Reading Tabular Data into DataFrames

pandas library good for reading tabular data, statistics, spreadsheets etc
similar to R's dataframes
2d table, named columns, possibly different data types
import pandas, read data with pandas.read_csv function 
you'll need the gap minder data now, we need the full path to the file

```import pandas```
```data = pandas.read_csv('/home/colin/Work/SCW/pyton-novice-gapminder/data/gapminder_gdp_oceania.csv')```
```print(data)```

data is hard to read from the print statement, use the variable explorer instead

in this output row indicies are 0/1, not country names. We want country names.

```data = pandas.read_csv('data/gapminder_gdp_oceania.csv',index_col='country')```
```print(data)```

0/1 from start are now gone, country names at the start instead
find out more info with ```data.info()```
shows data types, number of columns, row names, non-null (not empty), memory use

DataFrame.columns tells us about the columns, this is a variable not a function. Called a member variable.

```print(data.columns)```


DataFrame.T to transpose, treat columns as rows or vice-versa, doesn't copy data just changes the view of it. Its another member variable.

```print(data.T)```

DataFrame.describe, fucntion to get summary stats for numerical columns. include='all' argument does all columns.

```print(data.describe())```

### Exercises
* reading other data
* inspecting data
* reading files in other directories
* writing data

### Summary 
* pandas can get basic stats on tabular data
* use index_col argument to read_csv to choose a column for row headings
* DataFrame.info gives more info about a dataframe
* DataFrame.columns info about columns
* DataFrame.T transposes
* DataFrame.describe summary stats 

## Pandas DataFrames

We can specify which bit of the dataframe to get numerically. They are 2D arrays, zero based. We saw this earlier with strings, but only 1 dimensional. Demonstrate from data view in spyder. data.iloc lets us do this. 

```import pandas```
```data = pandas.read_csv('data/gapminder_gdp_europe.csv',index_col='country')```
```print(data.iloc[0,0])```

gives 1601.056136, GDP for Albania. Remove index_col and it will say Albania.

data.loc lets us do the same thing but uses column/row names. 

```print(data.loc["Albania","gdpPercap_1952"])```

If we want all rows the : operator will do that

```print(data.loc["Albania",:])```

Same achieved without the colon

```print(data.loc["Albania"])```

We can get the second index instead:

```print(data.loc[:,"gdpPercap_1952"])```

alternatives:

```print(data.loc["gdpPercap_1952"])```
```print(data.gdpPercap_1952)```

we can also select multiple rows, the : operator means between in this case. Reminder that this is called slicing. 

```print(data.loc['Italy':'Poland','gdpPercap_1952':'gdpPercap_1972'])```

Slices can be used in another operation
```print(data.loc['Italy':'Poland','gdpPercap_1952':'gdpPercap_1972'].max())```
or
```print(data.loc['Italy':'Poland','gdpPercap_1952':'gdpPercap_1972'].min())```

subsets of data can be copied to another dataframe 

```# Use a subset of data to keep output readable.```
```subset = data.loc['Italy':'Poland', 'gdpPercap_1962':'gdpPercap_1972']```
```print('Subset of data:\n', subset)```

pandas can do querying based on certain conditions. Here we check for values over 10,000. 


```# Which values were greater than 10000 ?```
```print('\nWhere are values large?\n', subset > 10000)```

A mask can be created to block out values that don't meet our criteria. These will be changed to NaN (not a number)

```mask = subset > 10000```
```print(subset[mask]```

We can get some summary stats by doing describe on the masked subset. NaNs are ignored by the statistical operations.

```print(subset[subset > 10000].describe())```

### Exercises
* selection of individual values
* extent of slicing
* reconstructing data
* selecting indicies
* practice with selection
* thought exercise on data interpretation

### Summary
* use iloc to select by integer value, loc to select by name
* : means all rows or columns, slice a range between two values with :
* make comparisons of the data and extract a subset
* masks to mask out certain data for performing stats
* masks turn to NaNs

## Plotting

Configure where plots appear with Tools->Preferences->IPython Console then graphics tab. Inline for inline display in the console and automatic for their own window. Close iPython console and let it reload.

```import matplotlib.pyplot as plt```
```time = [0, 1, 2, 3]```
```position = [0, 100, 200, 300]```

```plt.xlabel('Time (hr)')```
```plt.ylabel('Position (km)')```
```plt.plot(time, position)```

We can plot data from a pandas dataframe instead of a list. DataFrame.plot implicitly calls matplotlib's plot function, it also imports matplotlib for us. 

```import pandas```
```data = pandas.read_csv('data/gapminder_gdp_oceania.csv', index_col='country')```
```data.loc['Australia'].plot()```
```plt.xticks(rotation=90)```

Rows (years in this case) will be x-axis, transpose data to change this.

```data.T.plot()```
```plt.ylabel('GDP per captia')```
```plt.xticks(rotation=90)```

Other styles can be done such bar charts.

```plt.style.use('ggplot')```
```data.T.plot(kind='bar')```
```plt.xticks(rotation=90)```
```plt.ylabel('GDP per capita')```

annoying having gdpPercap_year in labels, we just want year 
strip function will remove some text

```years = data.columns.str.strip('gdpPercap_')```

just have Australia data
```gdp_australia = data.loc['Australia']```

use g-- style to have dashed lines
```plt.plot(years, gdp_australia, 'g--')```

now plot several data sets together to combine Australia and New Zealand again
```# Select two countries' worth of data.```
```gdp_australia = data.loc['Australia']```
```gdp_nz = data.loc['New Zealand']```

```# Plot with differently-colored markers.```
```plt.plot(years, gdp_australia, 'b-', label='Australia')```
```plt.plot(years, gdp_nz, 'g-', label='New Zealand')```

```# Create legend.```
```plt.legend(loc='upper left')```
```plt.xlabel('Year')```
```plt.ylabel('GDP per capita ($)')```

Change into a scatter diagram, correlating the two data sets

```plt.scatter(gdp_australia,gdp_nz)```

label axes 

```plt.xlabel('Australia')```
```plt.ylabel('New Zealand')```

### Exercises 
* minima and maxima
* correlations
* more correlations

### Summary
* matplotlib popular way to plot things in python
* we can plot directly from a pandas dataframe, indirectly calls matplotlib
* workflow: select data, transform it, plot it
* many plot styles available
* can plot multiple data sets together
https://matplotlib.org/gallery/index.html for examples of what matplotlib can do
