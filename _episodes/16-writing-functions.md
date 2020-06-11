---
title: "Writing Functions"
teaching: 10
exercises: 15
questions:
- "How can I create my own functions?"
objectives:
- "Explain and identify the difference between function definition and function call."
- "Write a function that takes a small, fixed number of arguments and produces a single result."
keypoints:
- "Break programs down into functions to make them easier to understand."
- "Define a function using `def` with a name, parameters, and a block of code."
- "Defining a function does not run it."
- "Arguments in call are matched to parameters in definition."
- "Functions may return a result to their caller using `return`."
---
## Break programs down into functions to make them easier to understand.

*   Human beings can only keep a few items in working memory at a time.
*   Understand larger/more complicated ideas by understanding and combining pieces.
    *   Components in a machine.
    *   Lemmas when proving theorems.
*   Functions serve the same purpose in programs.
    *   *Encapsulate* complexity so that we can treat it as a single "thing".
*   Also enables *re-use*.
    *   Write one time, use many times.

## Define a function using `def` with a name, parameters, and a block of code.

*   Begin the definition of a new function with `def`.
*   Followed by the name of the function.
    *   Must obey the same rules as variable names.
*   Then *parameters* in parentheses.
    *   Empty parentheses if the function doesn't take any inputs.
    *   We will discuss this in detail in a moment.
*   Then a colon.
*   Then an indented block of code.

~~~
def print_greeting():
    print('Hello!')
~~~
{: .language-python}

## Defining a function does not run it.

*   Defining a function does not run it.
    *   Like assigning a value to a variable.
*   Must call the function to execute the code it contains.

~~~
print_greeting()
~~~
{: .language-python}
~~~
Hello!
~~~
{: .output}

## Arguments in call are matched to parameters in definition.

*   Functions are most useful when they can operate on different data.
*   Specify *parameters* when defining a function.
    *   These become variables when the function is executed.
    *   Are assigned the arguments in the call (i.e., the values passed to the function).
    *   If you don't name the arguments when using them in the call, the arguments will be matched to
parameters in the order the parameters are defined in the function.

~~~
def print_date(year, month, day):
    joined = str(year) + '/' + str(month) + '/' + str(day)
    print(joined)

print_date(1871, 3, 19)
~~~
{: .language-python}
~~~
1871/3/19
~~~
{: .output}

Or, we can name the arguments when we call the function, which allows us to
specify them in any order:
~~~
print_date(month=3, day=19, year=1871)
~~~
{: .language-python}
~~~
1871/3/19
~~~
{: .output}

*   Via [Twitter](https://twitter.com/minisciencegirl/status/693486088963272705):
    `()` contains the ingredients for the function
    while the body contains the recipe.

## Functions may return a result to their caller using `return`.

*   Use `return ...` to give a value back to the caller.
*   May occur anywhere in the function.
*   But functions are easier to understand if `return` occurs:
    *   At the start to handle special cases.
    *   At the very end, with a final result.

~~~
def average(values):
    if len(values) == 0:
        return None
    return sum(values) / len(values)
~~~
{: .language-python}

~~~
a = average([1, 3, 4])
print('average of actual values:', a)
~~~
{: .language-python}
~~~
2.6666666666666665
~~~
{: .output}

~~~
print('average of empty list:', average([]))
~~~
{: .language-python}
~~~
None
~~~
{: .output}

*   Remember: [every function returns something]({{ page.root }}/04-built-in/).
*   A function that doesn't explicitly `return` a value automatically returns `None`.

~~~
result = print_date(1871, 3, 19)
print('result of call is:', result)
~~~
{: .language-python}
~~~
1871/3/19
result of call is: None
~~~
{: .output}


> ## Using Functions With Conditionals in Pandas
>
> Functions will often contain conditionals.  Here is a short example that
> will indicate which quartile the argument is in based on hand-coded values
> for the quartile cut points.
>
> ~~~
> def calculate_life_quartile(exp):
>     if exp < 58.41:
>         # This observation is in the first quartile
>         return 1
>     elif exp >= 58.41 and exp < 67.05:
>         # This observation is in the second quartile
>        return 2
>     elif exp >= 67.05 and exp < 71.70:
>         # This observation is in the third quartile
>        return 3
>     elif exp >= 71.70:
>         # This observation is in the fourth quartile
>        return 4
>     else:
>         # This observation has bad data
>        return None
>
> calculate_life_quartile(62.5)
> ~~~
> {: .language-python}
>
> ~~~
> 2
> ~~~
> {: .output}
>
> That function would typically be used within a `for` loop, but Pandas has
> a different, more efficient way of doing the same thing, and that is by
> *applying* a function to a dataframe or a portion of a dataframe.  Here
> is an example, using the definition above.
>
> ~~~
> data = pd.read_csv('data/Americas-lifeExp.csv', index_col='country')
> data['life_qrtl'] = data['lifeExp'].apply(calculate_life_quartile)
> ~~~
> {: .language-python}
>
> There is a lot in that second line, so let's take it piece by piece.
> On the right side of the `=` we start with `data['lifeExp']`, which is the
> column in the dataframe called `data` labeled `lifExp`.  We use the
> `apply()` to do what it says, apply the `calculate_life_quartile` to the
> value of this column for every row in the dataframe.
{: .callout}


> ## Identifying Syntax Errors
>
> 1. Read the code below and try to identify what the errors are
>    *without* running it.
> 2. Run the code and read the error message.
>    Is it a `SyntaxError` or an `IndentationError`?
> 3. Fix the error.
> 4. Repeat steps 2 and 3 until you have fixed all the errors.
>
> ~~~
> def another_function
>   print("Syntax errors are annoying.")
>    print("But at least python tells us about them!")
>   print("So they are usually not too hard to fix.")
> ~~~
> {: .language-python}
>
> > ## Solution
> >
> > ~~~
> > def another_function():
> >   print("Syntax errors are annoying.")
> >   print("But at least Python tells us about them!")
> >   print("So they are usually not too hard to fix.")
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Definition and Use
>
> What does the following program print?
>
> ~~~
> def report(pressure):
>     print('pressure is', pressure)
>
> print('calling', report, 22.5)
> ~~~
> {: .language-python}
> > ## Solution
> >
> > ~~~
> > calling <function report at 0x7fd128ff1bf8> 22.5
> > ~~~ 
> > {: .output}
> >
> > A function call always needs parenthesis, otherwise you get memory address of the function object. So, if we wanted to call the function named report, and give it the value 22.5 to report on, we could have our function call as follows
> > ~~~
> > print("calling")
> > report(22.5)
> > ~~~
> {: .solution}
{: .challenge}


> ## Order of Operations
>
> The example above:
>
> ~~~
> result = print_date(1871, 3, 19)
> print('result of call is:', result)
> ~~~
> {: .language-python}
>
> printed:
> ~~~
> 1871/3/19
> result of call is: None
> ~~~
> {: .output}
>
> Explain why the two lines of output appeared in the order they did.
>
> What's wrong in this example?
> ~~~
> result = print_date(1871,3,19)
>
> def print_date(year, month, day):
>    joined = str(year) + '/' + str(month) + '/' + str(day)
>    print(joined)
> ~~~
> {: .language-python}
> 
> > ## Solution
> > 
> > 1. The first line of output (`1871/3/19`) is from the print function inside `print_date()`, while the second line
> > is from the print function below the function call. All of the code inside `print_date()` is executed first, and
> > the program then "leaves" the function and executes the rest of the code.   
> > 2. The problem with the example is that the function is defined *after* the call to the function is made. Python
> > therefore doesn't understand the function call.
> {: .solution}
{: .challenge}

> ## Encapsulation
>
> Fill in the blanks to create a function that takes a single filename as an argument,
> loads the data in the file named by the argument,
> and returns the minimum value in that data.
>
> ~~~
> import pandas
>
> def min_in_data(____):
>     data = ____
>     return ____
> ~~~
> {: .language-python}
> > ## Solution
> >
> > ~~~
> > import pandas
> > 
> > def min_in_data(filename):
> >     data = pandas.read_csv(filename)
> >     return data.min()
> > ~~~
> {: .language-python}
> {: .solution}
{: .challenge}

> ## Find the First
>
> Fill in the blanks to create a function that takes a list of numbers as an argument
> and returns the first negative value in the list.
> What does your function do if the list is empty?
>
> ~~~
> def first_negative(values):
>     for v in ____:
>         if ____:
>             return ____
> ~~~
> {: .language-python}
> > ## Solution
> >
> > ~~~
> > def first_negative(values):
> >     for v in values:
> >         if v<0:
> >             return v
> > ~~~
> > {: .language-python}
> > If an empty list is passed to this function, it returns `None`:
> > ~~~
> > my_list = []
> > print(first_negative(my_list)
> > ~~~
> > {: .language-python}
> > ~~~
> > None
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}

> ## Calling by Name
>
> Earlier we saw this function:
>
> ~~~
> def print_date(year, month, day):
>     joined = str(year) + '/' + str(month) + '/' + str(day)
>     print(joined)
> ~~~
> We saw that we can call the function using *named arguments*, like this:
> ~~~
> print_date(day=1, month=2, year=2003)
> ~~~
> {: .language-python}
>
> 1.  What does `print_date(day=1, month=2, year=2003)` print?
> 2.  When have you seen a function call like this before?
> 3.  When and why is it useful to call functions this way?
> {: .language-python}
> > ## Solution
> > 
> > 1. `2003/2/1`
> > 2. We saw examples of using *named arguments* when working with the pandas library. For example, when reading in a dataset 
> > using `data = pandas.read_csv('data/gapminder_gdp_europe.csv', index_col='country')`, the last argument `index_col` is a 
> > named argument.  
> > 3. Using named arguments can make code more readable since one can see from the function call what name the different arguments 
> > have inside the function. It can also reduce the chances of passing arguments in the wrong order, since by using named arguments 
> > the order doesn't matter.
> {: .solution}
{: .challenge}

> ## Encapsulate of If/Print Block
>
> The code below will run on a label-printer for chicken eggs.  A digital scale will report a chicken egg mass (in grams) to the computer and then the computer will print a label.  
>
> Please re-write the code so that the if-block is folded into a function.
>
> ~~~
>  import random
>  for i in range(10):
>
>     # simulating the mass of a chicken egg
>     # the (random) mass will be 70 +/- 20 grams
>     mass=70+20.0*(2.0*random.random()-1.0)
>
>     print(mass)
>    
>     #egg sizing machinery prints a label
>     if(mass>=85):
>        print("jumbo")
>     elif(mass>=70):
>        print("large")
>     elif(mass<70 and mass>=55):
>        print("medium")
>     else:
>        print("small")
> ~~~
> {: .language-python}
>
>
> The simplified program  follows.  What function definition will make it functional?
>
> ~~~
>  # revised version
>  import random
>  for i in range(10):
>
>     # simulating the mass of a chicken egg
>     # the (random) mass will be 70 +/- 20 grams
>     mass=70+20.0*(2.0*random.random()-1.0)
>
>     print(mass,print_egg_label(mass))    
>
> ~~~
> {: .language-python}
>
>
> 1. Create a function definition for `print_egg_label()` that will work with the revised program above.  Note, the function's return value will be significant. Sample output might be `71.23 large`.
> 2.  A dirty egg might have a mass of more than 90 grams, and a spoiled or broken egg will probably have a mass that's less than 50 grams.  Modify your `print_egg_label()` function to account for these error conditions. Sample output could be `25 too light, probably spoiled`.
>
> > ## Solution
> >
> > ~~~
> > def print_egg_label(mass):
> >     #egg sizing machinery prints a label
> >     if(mass>=90):
> >         return("warning: egg might be dirty")
> >     elif(mass>=85):
> >         return("jumbo")
> >     elif(mass>=70):
> >         return("large")
> >     elif(mass<70 and mass>=55):
> >         return("medium")
> >     elif(mass<50):
> >         return("too light, probably spoiled")
> >     else:
> >         return("small")
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Encapsulating Data Analysis
>
> 1. Complete the blanks in the following code, which calculates the average Japanese GDP in the 1980s.
>
> ~~~
> import pandas
>
> def avg_gdp_in_decade(country, continent, year):
>     df = pandas.read_csv('data/gapminder_gdp_'+___+'.csv',delimiter=',',index_col=0)
>     country_data = df.loc[country]
>     gdp_decade = 'gdpPercap_' + str(year // ____) 
>     avg = (country_data.loc[gdp_decade + ____ ] + country_data.loc[gdp_decade + ____ ]) / 2
>     return avg
>
> df = pandas.read_csv('data/gapminder_gdp_asia.csv', index_col=0)
> 
> print('The average GDP for Japan in the 1980s was',avg_gdp_in_decade('Japan','asia',1980))
> ~~~
> {: .language-python}
>
> 2. How would you generalize this function 
>    if you did not know beforehand that the GDP data would only be in years ending with 2 and 7?
>    For instance, what if we also had data from years ending in 1 and 9 for each decade?
>    (Hint: use a for loop to go through each data column from dataframe.index, checking which decade they are in)
>
> > ## Solution
> >
> > 1.
> >
> > ~~~
> > import pandas
> > 
> > def avg_gdp_in_decade(country, continent, year):
> >    df = pandas.read_csv('data/gapminder_gdp_'+ continent +'.csv',delimiter=',',index_col=0)
> >    country_data = df.loc[country]
> >    gdp_decade = 'gdpPercap_' + str(year // 10) 
> >    avg = (country_data.loc[gdp_decade + '2' ] + country_data.loc[gdp_decade + '7' ]) / 2
> >    return avg
> >
> > print('The average GDP for Japan in the 1980s was',avg_gdp_in_decade('Japan','asia',1980))
> > ~~~
> > {: .language-python}
> >
> > {: .language-python}
> >
> > 3.
> > 
> > We need to loop over the reported years
> >    to obtain the average for the relevant ones in the data.
> >
> > ~~~
> > def avg_gdp_in_decade(country, continent, year):
> >     df = pandas.read_csv('data/gapminder_gdp_' + continent + '.csv', index_col=0)
> >     country_data = df.loc[country]
> >     gdp_decade = 'gdpPercap_' + str(year // 10)
> >     total = 0.0
> >     num_years = 0
> >     for yr_header in country_data.index: # country_data's index contains reported years
> >         if yr_header.startswith(gdp_decade):
> >             total = total + country_data.loc[yr_header]
> >             num_years = num_years + 1
> >     return total/num_years
> >
> > print('The average GDP for Japan in the 1980s was',avg_gdp_in_decade('Japan','asia',1980))
> > ~~~
> > The result should be: 
> > 
> > ~~~
> > The average GDP for Japan in the 1980s was 20880.023800000003
> > ~~~
> > {: .output}
> {: .solution}
{: .challenge}



> ## Converting celcius to farenheit
>
> Degrees celcius to farenheit can be converted by multiplying by 9/5 and adding 32. 
> ~~~
> farenheit = (celcius * 9/5) + 32
> ~~~
> {: .language-python}
>
>
> 1. Define a function called `celcius_to_farenheit` that takes the input celcius_temp and returns the value in farenheit.
>
> 2. Using a `for` loop, generate the farenheit values for evey celcius temperature between 0 and 35 at 5 degree intervals and display both values.
>
> 3. Encapsulate the logic of your `for` loop into a function called `conversion_table` that will display a heading "C  F" and then display the celcius and corresponding farenheit temperature on each line.
>
>
> > ## Solution
> >
> > 1.
> >
> > ~~~
> > def celcius_to_farenheit(celcius_temp):
> >     return (celcius_temp * 9/5) + 32
> > ~~~
> > {: .language-python}
> >
> > 2.
> >
> > ~~~
> > for c in range(0, 35,5):
> >     print(c,celcius_to_farenheit(c))
> > ~~~
> > {: .language-python}
> >
> > 3.
> > ~~~
> > def conversion_table():
> >     print("C / F")
> >     for c in range(0, 35,5):
> >         print(c,celcius_to_farenheit(c))
> > ~~~
> > {: .language-python}
> {: .solution}
{: .challenge}

> ## Using Functions With Conditionals in Pandas
>
> Functions will often contain conditionals.  Here is a short example that
> will indicate which quartile the argument is in based on hand-coded values
> for the quartile cut points.
>
> ~~~
> def calculate_life_quartile(exp):
>     if exp < 58.41:
>         # This observation is in the first quartile
>         return 1
>     elif exp >= 58.41 and exp < 67.05:
>         # This observation is in the second quartile
>        return 2
>     elif exp >= 67.05 and exp < 71.70:
>         # This observation is in the third quartile
>        return 3
>     elif exp >= 71.70:
>         # This observation is in the fourth quartile
>        return 4
>     else:
>         # This observation has bad data
>        return None
>
> calculate_life_quartile(62.5)
> ~~~
> {: .language-python}
>
> ~~~
> 2
> ~~~
> {: .output}
>
> That function would typically be used within a `for` loop, but Pandas has
> a different, more efficient way of doing the same thing, and that is by
> *applying* a function to a dataframe or a portion of a dataframe.  Here
> is an example, using the definition above.
>
> ~~~
> data = pd.read_csv('Americas-data.csv')
> data['life_qrtl'] = data['lifeExp'].apply(calculate_life_quartile)
> ~~~
> {: .language-python}
>
> There is a lot in that second line, so let's take it piece by piece.
> On the right side of the `=` we start with `data['lifeExp']`, which is the
> column in the dataframe called `data` labeled `lifExp`.  We use the
> `apply()` to do what it says, apply the `calculate_life_quartile` to the
> value of this column for every row in the dataframe.
{: .callout}

