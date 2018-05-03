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

## Variables and Assignment

### Variables 

* variables store values, text or number
* = assigns from right to left

```age = 42```
```first_name = ahmed```

* explain variable explorer
* explain variable names can only be letters, digits and underscores. Cannot start with a digit
* double underscore at the start has special meaning


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




