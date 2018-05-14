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

### Exercises
* swapping values
* predicting values
* substrings of numbers
* choosing variable names
* slicing 

### Summary
* variables store values, print displays them
* variables must be created before use
* can be used in calculations
* use an index to get single characters from a string
* slices to get substrings
* len function gives string length
* variable names case sensitive, don't use spaces in names, make names meaningful

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

## End of day 1
* feedback, most important thing I learned today
* one thing I want further clarification of

Go watch joy of stats, https://www.gapminder.org/videos/the-joy-of-stats/

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


## Lists

using hundreds+ variables would get tedious and complicated

lists store multiple variables together as one

use [ and ] to index a list

values separated by commas 

len gives the number of items in a list

```pressures = [ 0.273, 0.275, 0.277, 0.275, 0.276]```
```print('pressures:',pressures)```
```print('length:',len(pressures))```

we can fetch single items from a list with an index, just like we did with strings 

```print('zeroth item from pressures:',pressures[0])```
```print('fourth item from pressures:',pressures[4])```

we can change the contents of a list item by assigning it

```pressures[0] = 0.265```
```print(pressures)```

Extra items can be added with the append method.

```primes = [2,3,5]```
```print('primes is initially:',primes)```
```primes.append(7)```
```primes.append(9)```
```print('primes has become:',primes)```

methods are like functions but apply to a particular object (list in this case). objectname.method_name 
we used these already with dataframes 

help(list) shows a list of them

extend method is similar to append but combines two lists

```teen_primes = [11, 13, 17, 19]```
```middle_aged_primes = [37, 41, 43, 47]```
```print('primes is currently:', primes)```
```primes.extend(teen_primes)```
```print('primes has now become:', primes)```

we can also append lists, but then we end up with a list within a list

```primes.append(middle_aged_primes)```
```print('primes has finally become:', primes)```

items are removed from a list with del
different syntax

```del primes[4]```

empty lists are defined by []
useful if we want an empty list declared to use later on

lists can contain different types

```goals = [ 1, 'Create lists.', 2, 'Extract items from lists.', 3,'Modify lists.']```

remember that character strings work like lists for getting single characters

```element = 'carbon'```
```print('zeroth character:',element[0])```
```print('third character:',element[3])```

character strings are immutable, we can't change single characters after we create the string
lists are mutable and can be changed. Both are types of collections.

```element[0] = 'C'```

results in error

going beyond the end of the list causes an error. This is a runtime error, can't be detected in advance as we might not know how long the list will be.

```print('99th element is',element[99])```
```print(goals[99])```

### Exercises
* fill in the blanks, shows list slicing
* how large is a slice
* from strings to lists and back, introduces list function to convert strings to lists
* working with the end, negative slicing, removes the end
* stepping through a list, list strides (intervals)
* slice bounds, -1:3 returns nothing trying to go backwards
* sorting, sorted returns the sorted list, leaves original alone. sort modifies original. 
* copying, this does a copy by reference in A and copy by value in B


### Summary

* A list stores many values in a single structure.
* Use an item’s index to fetch it from a list.
* Lists’ values can be replaced by assigning to them.
* Appending items to a list lengthens it.
* Use del to remove items from a list entirely.
* The empty list contains no values.
* Lists may contain values of different types.
* Character strings can be indexed like lists.
* Character strings are immutable.
* Indexing beyond the end of the collection is an error.

## For Loops

executes a command for every value in a collection 

```for number in [2,3,5]:```
```    print(number)```

equivalent of doing:
```print(2)```
```print(3)```
```print(5)```

body of the for loop must be indented
one indent is usually four spaces or one tab

```for number in [2,3,5]:```
```print(number)```

above causes indention error

```firstName="jon"```
```    lastName="smith```

above causes unexpected indent error

for loops are made up of a collection, loop variable and body

```for number in [2,3,5]:```
```    print(number)```

in above, [2,3,5] is the collection, print(number) is the body and number is the variable
loop variables can be called anything


```for kitten in [2,3,5]:```
```    print(kitten)```

body can contain many statements, should only be a few lines at most for human readability

```primes = [2,3,5]```
```for p in primes:```
```    squared = p ** 2```
```    cubed = p ** 3```
```    print(p,squared,cubed)```

The range built in function can be used to iterate over a sequence of numbers. A range is not a list and the numbers are generated on the fly.

```print(range(0,3))```
```for number in range(0,3):```
```    print(number)```

range(N) = 0 to N-1
range(1,N) = 1 to N-1

accumulator pattern: initialise accumulator variable to zero/empty string/list, update it  using variables from the collection

code to add up all numbers up to 10
```total = 0```
```for number in range(10):```
```    total = total + (number+1)```
```print(total)```

total = total + number(+1) means add the current value of total to the current number +1
we use number +1 instead of just number because the loop is 0 to 9 not 1 to 10

### Exercises
* classifying errors
* tracing execution, strings work as collections to use in a for loop
* reverse a string
* practice accumulating, strings in a list get counted as whole strings in the loop variable
* cumulative sum, += operator, shorthand for var = var +
* identifying variable name errors, % divides and gives remainder. Returns zero when number is a multiple.
* identifying item errors, 

### Summary
* A for loop executes commands once for each value in a collection.
* The first line of the for loop must end with a colon, and the body must be indented.
* Indentation is always meaningful in Python.
* A for loop is made up of a collection, a loop variable, and a body.
* Loop variables can be called anything (but it is strongly advised to have a meaningful name to the looping variable).
* The body of a loop can contain many statements.
* Use range to iterate over a sequence of numbers.
* The Accumulator pattern turns many values into one.

## Looping Over Data Sets
For loops can be used to loop over a list of filenames and process each one in turn

```import pandas```
```for filename in ['data/gapminder_gdp_africa.csv', 'data/gapminder_gdp_asia.csv']:```
```    data = pandas.read_csv(filename, index_col='country')```
```    print(filename, data.min())```

This will process the gap minder Africa and Asia data and print the minimum GDP for each 

globbing matches a set of files with a pattern, like wildcards in the shell
'*' means zero or more characters
'?' neabs exactly one character
glob library has useful globbing functions, glob.glob('pattern') returns a list of matching files

```import glob```
```print('all csv files in the data directory:',glob.glob('data/*.csv'))```

above lists all CSV files in the data directory

```print('all pdb files:',glob.glob('*.pdb'))```

list all pdb files in current directory, should be an empty list

We can use glob and for to process patches of files. Helps if files are named consistenly.

```for filename in glob.glob('data/gapminder_*.csv'):```
```    data = pandas.read_csv(filename)```
```    print(filename, data['gdpPercap_1952'].min())```

this will print the minimum 1952 GDP for each continent

### Exercises

* determining matches 
* minimum file size, introduces tuples
* comparing data, brings everything together, start by printing the answer, then graph it

### Summary
* Use a for loop to process files given a list of their names.
* Use glob.glob to find sets of files whose names match a pattern.
* Use glob and for to process batches of files.



## Conditionals

decides whether or not to execute some code based on a Condition.
conditons can be > (greater than) >= (greater than or equal to) <= (less than or equal) < (less than), == (equal), != (not equal)

similar structure to for loops, if, condition, colon. Code which if statement executes is indented.

```mass = 3.54```
```if mass > 3.0:```
```    print(mass, 'is large')```
```mass = 2.07```
```if mass > 3.0:```
```    print(mass, 'is large')```

displays 3.54 is large, but not 2.07 is large

conditionals often used in loops to evaluate each member of a collection.

``masses = [3.54, 2.07, 9.22, 1.86, 1.71]``
``for m in masses:``
```    if m > 3.0:```
```        print(m, 'is large')````

else statement specifies what happens when if condition isn't true

```masses = [3.54, 2.07, 9.22, 1.86, 1.71]```
```for m in masses:```
```    if m > 3.0:```
```        print(m, 'is large')```
```    else:```
```        print(m, 'is small')```

elif makes a second comparison if the first one is false
there can be several of these following an if
follow the last elif with an else to catch any condition which hasn't been caught by the if/elifs

```masses = [3.54, 2.07, 9.22, 1.86, 1.71]```
```for m in masses:```
```    if m > 9.0:```
```        print(m, 'is HUGE')```
```    elif m > 3.0:```
```        print(m, 'is large')```
```    else:```
```        print(m, 'is small')```

Each condition will be checked in the order it appears. Can cause problems if you get things the wrong way.

```grade = 85```
```if grade >= 70:```
```    print('grade is C')```
```elif grade >= 80:```
```    print('grade is B')```
```elif grade >= 90:```
```    print('grade is A')```

outputs C, because 85 is greater than 70. Once that's been found to be true it doesn't try anything else.

if doesn't go back and recheck things when they change.

```velocity = 10.0```
```if velocity > 20.0:```
```    print('moving too fast')```
```else:```
```    print('adjusting velocity')```
```    velocity = 50.0```

This won't recheck with velocity = 50.0


conditionals can be used to evolve the state of a variable over time 

```velocity = 10.0```
```for i in range(5): # execute the loop 5 times```
```    print(i, ':', velocity)```
```    if velocity > 20.0:```
```        print('moving too fast')```
```        velocity = velocity - 5.0```
```    else:```
```        print('moving too slow')```
```        velocity = velocity + 10.0```
```print('final velocity:', velocity)```

It can be useful for debugging to create a table of values at each iteration of the loop

multiple conditions can be checked at once with the "and" or "or" keywords. brackets can be used to group statements too.

```mass     = [ 3.54,  2.07,  9.22,  1.86,  1.71]```
```velocity = [10.00, 20.00, 30.00, 25.00, 20.00]```

```i = 0```
```for i in range(5):```
```    if mass[i] > 5 and velocity[i] > 20:```
```        print("Fast heavy object.  Duck!")```
```    elif mass[i] > 2 and mass[i] <= 5 and velocity[i] <= 20:```
```        print("Normal traffic")```
```    elif mass[i] <= 2 and velocity[i] <= 20:```
```        print("Slow light object.  Ignore it")```
```    else:```
```        print("Whoa!  Something is up with the data.  Check it")```

instead of ```if mass[i] <= 2 or mass[i] >= 5 and velocity[i] > 20:```

write one of these:

```if (mass[i] <= 2 or mass[i] >= 5) and velocity[i] > 20:```
```if mass[i] <= 2 or (mass[i] >= 5 and velocity[i] > 20):```


### Excercises
* tracing execution
* trimming values
* processing small files
* Checking if values are None, uses % operator 

### Summary
* Use if statements to control whether or not a block of code is executed.
* Conditionals are often used inside loops.
* Use else to execute a block of code when an if condition is not true.
* Use elif to specify additional tests.
* Conditions are tested once, in order.
* Create a table showing variables’ values to trace a program’s execution.


## Writing Functions

We can write our own functions to break down the code into manageable chunks. 
Encapsulate a single task into a function. 
Avoid repetition and enable reuse. 

Begin writing a function with def, followed by function name, open brackets,  close brackets, colon
ident function body


```def print_greeting():```
```    print('Hello')```

definig a function doesn't run it, it has to be explicitly called

```print_greeting()```

parameters are defined between the ( and ), separate each by a comma

nice analogy, () contains the ingredients, after the : contains the recipie.

arguments given when calling must match the parameters we define
each argument is assigned to a variable of the corresponding parameter, in the same order
optionally you can name them when calling 

```def print_date(year,month,day):```
```    joined = str(year) + '/' + str(month) + '/' + str(day)```
```    print(joined)```
```print_date(1871,3,19)```

or we can name the parameters when calling

```print_date(month=3,day=19,year=1871)```

functions can return a value using the return statement. 
Return causes the function to exit. Returns can occur anywhere in the function, sometimes within if statements. More complex functions may contain multiple return statements.

```def average(values):```
```    if len(values) == 0:```
```        return None```
```    return sum(values) / len(values)```

```a = average([1, 3, 4])```
```print('average =',a)``` 
gives 2.66666

```print('average of empty list is:',average([]))```


Without a return statement a function still returns None, when it reaches its end

```result = print_date(1871, 3, 19)```
```print('result of call is:', result)```


pandas can apply a function to each item in a dataframe for you.

```data = pd.read_csv('Americas-data.csv')```
```data['life_qrtl'] = data['lifeExp'].apply(calculate_life_quartile)```

will apply calculate_life_quartile to every item in data['lifeExp'] and store it in data['life_qrtl']

```def calculate_life_quartile(exp):```
```    if exp < 58.41:```
```        # This observation is in the first quartile```
```        return 1```
```    elif exp >= 58.41 and exp < 67.05:```
```        # This observation is in the second quartile```
```       return 2```
```    elif exp >= 67.05 and exp < 71.70:```
```        # This observation is in the third quartile```
```       return 3```
```    elif exp >= 71.70:```
```        # This observation is in the fourth quartile```
```       return 4```
```    else:```
```        # This observation has bad data```
```       return None```

### Exercises
* identifying syntax errors
* definition and use
* order or operations
* encapsulation
* find the first
* calling by name
* Encapsulate if/print block
* encapsulate data analysis, assume that each decade only has data for years ending 2 and 7
* temperature conversion

### Summary
* Break programs down into functions to make them easier to understand.
* Define a function using def with a name, parameters, and a block of code.
* Defining a function does not run it.
* Arguments in call are matched to parameters in definition.
* Functions may return a result to their caller using return.

## Programming Style

use meaingful variable and function names
write comments
use spaces not tabs to ident
encapsulate in functions for re-use
don't reinvent the wheel, use what libraries provide you

PEP8 coding standard suggests a standard way everyone should write python. 
Enable this by going to preferences, editor, code introspection/analysis, tick "real-time code style analysis"
Yellow triangles will appear on lines with problems. Same applies to syntax errors. 

alternatively run pep8 command from command line or paste into http://pep8online.com/
better to check as you type

use assertions to check for internal errors in code

```def calc_bulk_density(mass, volume):```
```    '''Return dry bulk density = powder mass / powder volume.'''```
```    assert volume > 0```
```    return mass / volume```

Causes a run time error if volume isn't greater than 0. Assertions should only check things, they shouldn't change any variables. 

docstrings document what a function does. Should be the first line after the def. Start with double quotes "
Will display when help is called. can span multiple lines. 

```def average(values):```
```    "Return average of values, or None if no values are supplied."```

```    if len(values) == 0:```
```        return None```
```    return sum(values) / average(values)```

```help(average)```

### Exercises
* what will be shown
* document this
* code cleanup 

### Summary
* Follow standard Python style in your code.
* Use docstrings to provide online help.

## Wrap up

What Python to use?

Anaconda, provides everything you need in one package. Its large and some people don't want to install it.

miniconda/conda, use the anaconda package manager and can install just what you need. Much smaller than full blown anaconda. Won't include spyder or jyputer by default. 

Command line python, you'll have to install extra libraries yourself. System vs pip. Especially painful on Windows. You might have to do it this way on HPCs. 

Jyputer notebooks, embed notes with your code. Nice for student assignment or lab notebook styles. Web based, code potentially runs on another computer. Edited on the web.

Various other specialist distributions, owgeo4w (Open Source Geography for Windows) 

Python community

PyCon conference, SciPy utilities, NumPy, Pandas, SciKit Learn (machine learning)
biopython
GDAL
sympy (symbolic maths)
openCV






