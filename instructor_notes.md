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

* explain what print does
* functions called by writing their name followed by brackets with arguments
* strings must be in double or single quotes

```print(first_name,'is',age,'years old')```

* explain variables must exist before they are used

```print(last_name)```

causes NameError

* explain variables persisting across our console. Show closing the console to loose the state.

* explain variable calculations, strings vs integers

(rerun script to bring back prior state)
```age = age + 3```
```print('Age in three years:',age)```

* we get substrings using [x] where x is the index, starts from 0. error when it goes off the end

```atom_name = 'helium'```
```print(atom_name[0]``` 

* explain slice notation [x:y] gets all characters from position x to y-1

```print(atom_name[0:3]```

* len gets us string length. Functions can be nested, inner function evaluated first.

```print(len('helium'))```

* explain variable names are case sensitive. Use meaningful variable names. Python doesn't care, humans do.



