---
title: "Variables and Assignment"
teaching: 10
exercises: 10
questions:
- "How can I store data in programs?"
objectives:
- "Write programs that assign values to variables and perform calculations with those values."
- "Correctly trace value changes in programs that use assignment."
keypoints:
- "Use variables to store values."
- "Use `print` to display values."
- "Variables persist between cells."
- "Variables must be created before they are used."
- "Variables can be used in calculations."
- "Use an index to get a single character from a string."
- "Use a slice to get a substring."
- "Use the built-in function `len` to find the length of a string."
- "Python is case-sensitive."
- "Use meaningful variable names."
---
## Use variables to store values.

*   Variables are names for values.
*   In Python the `=` symbol assigns the value on the right to the name on the left.
*   The variable is created when a value is assigned to it.
*   Here, Python assigns an age to a variable `age`
    and a name in quotation marks to a variable `first_name`.

~~~
age = 42
first_name = 'Ahmed'
~~~
{: .python}

*   Variable names:
    *   cannot start with a digit
    *   cannot contain spaces, quotation marks, or other punctuation
    *   *may* contain an underscore (typically used to separate words in long variable names)
*   Underscores at the start like `__alistairs_real_age` have a special meaning
    so we won't do that until we understand the convention.

## Use `print` to display values.

*   Python has a built-in function called `print` that prints things as text.
*   Call the function (i.e., tell Python to run it) by using its name.
*   Provide values to the function (i.e., the things to print) in parentheses.
*   To add text to the printout, wrap the text in single quotations.
*   The values passed to the function are called 'arguments'

~~~
print(first_name, 'is', age, 'years old')
~~~
{: .python}
~~~
Ahmed is 42 years old
~~~
{: .output}

*   `print` automatically puts a single space between items to separate them.
*   And wraps around to a new line at the end.

## Python is case-sensitive.

*   Python thinks that upper- and lower-case letters are different,
    so `Name` and `name` are different variables.
*   There are conventions for using upper-case letters at the start of variable names
    so we will use lower-case letters for now.

## Use meaningful variable names.

*   Python doesn't care what you call variables as long as they obey the rules
    (alphanumeric characters and the underscore).

~~~
flabadab = 42
ewr_422_yY = 'Ahmed'
print(ewr_422_yY, 'is', flabadab, 'years old')
~~~
{: .python}

*   Use meaningful variable names to help other people understand what the program does.
*   The most important "other person" is your future self.

## Variables must be created before they are used.

*   If a variable doesn't exist yet, or if the name has been mis-spelled,
    Python reports an error.
    *   Unlike some languages, which "guess" a default value.

~~~
print(last_name)
~~~
{: .python}
~~~
---------------------------------------------------------------------------
NameError                                 Traceback (most recent call last)
<ipython-input-1-c1fbb4e96102> in <module>()
----> 1 print(last_name)

NameError: name 'last_name' is not defined
~~~
{: .error}

*   The last line of an error message is usually the most informative.
*   We will look at error messages in detail [later]({{ page.root }}/05-error-messages/).

> ## Variables Persist Between Cells
> Variables defined in one cell exist in all other cells once executed,
> so the relative location of cells in the notebook do not matter
> (i.e., cells lower down can still affect those above).
> Remember: Notebook cells are just a way to organize a program:
> as far as Python is concerned,
> all of the source code is one long set of instructions.
{: .callout}

## Variables can be used in calculations.

*   We can use variables in calculations just as if they were values.
    *   Remember, we assigned 42 to `age` a few lines ago.
    *   We update the value of a variable using its current value (`age + 3`)

~~~
age = age + 3
print('Age in three years:', age)
~~~
{: .python}
~~~
Age in three years: 45
~~~
{: .output}

## Text string.
Snippets of text are usually called a *string*. In Python, we denote a string using
the single `'` or double `"` quotes:

~~~
print('This is a string')
print("This is also a string")
~~~
{: .python}

~~~
This is a string
This is also a string
~~~
{: .output}

## Use an index to get a single character from a string.

*   The characters (individual letters, numbers, and so on) in a string are
    ordered. For example, the string 'AB' is not the same as 'BA'. Because of
    this ordering, we can treat the string as a list of characters.
*   Each position in the string (first, second, etc.) is given a number. This
    number is called an index or sometimes a subscript.
*   Indices are numbered from 0 rather than 1.
*   Use the position's index in square brackets to get the character at that
    position.

~~~
book_name = 'I Robot'
print(book_name[0])
~~~
{: .python}

~~~
I
~~~
{: .output}

## Use a slice to get a substring.

*   A part of a string is called a substring. A substring can be as short as a
    single character.
*   An item in a list is called an element. Whenever we treat a string as if it
    were a list, the string's elements are its individual characters.
*   A slice is a part of a string (or, more generally, any list-like thing).
*   We take a slice by using `[start:stop]`, where `start` is replaced with the
    index of the first element we want and `stop` is replaced with the index of
    the element just after the last element we want.
*   The difference between stop and start is the slice's length.
*   Taking a slice does not change the contents of the original string. Instead,
    the slice is a copy of part of the original string.

~~~
book_name = 'The Fellowship of the Ring'
print(book_name[0:3])
~~~
{: .python}
~~~
The
~~~
{: .output}

> ## When would I use this ?
> This can be very useful when we want to work with a fragment of text.
>
> ~~~
> text0 = 'walk'
> text1 = 'walking'
> text2 = 'walked'
> print(text0[0:4])
> print(text1[0:4])
> print(text2[0:4])
> ~~~
> {: .python}
>
>
> ~~~
> walk
> walk
> walk
> ~~~
> {: .output}
{: .callout}

## Use the built-in function `len` to find the length of a string.
Just like you've been using print() to make values appear on the screen, there
are many more functions to perform other tasks. One of the other essentials is
`len()`, which will return the length of what you pass it (watch out! Not all
things in Python have a length). You can pass it a string or a variable for a
string into the (), and len will tell you how long it is. For example,
`len("hello")` will say 5, because there are five letters in there. Almost
everything in Python has a length of some sort, which you'll learn about in
later lessons.

~~~
print(len('The Gunslinger'))
~~~
{: .python}
~~~
14
~~~
{: .output}

*   Nested functions are evaluated from the inside out.

> ## Assigning Values
>
> What is the final value of `position` in the program below?
> (Try to think what the value of `position` will be without running the program,
> then run the program to check your prediction.)
>
> ~~~
> initial = "left"
> position = initial
> initial = "right"
> print(position)
> ~~~
> {: .python}
> > ## Solution
> > "left"
> {: .solution}
{: .challenge}

> ## Choosing a Name
>
> Which is a better variable name, `m`, `min`, or `minutes`?
> Why?
> Hint: think about which code you would rather inherit
> from someone who is leaving the lab:
>
> 1. `ts = m * 60 + s`
> 2. `tot_sec = min * 60 + sec`
> 3. `total_seconds = minutes * 60 + seconds`
>
> > ## Solution
> >
> > `minutes` is better because `min` might mean something like "minimum"
> > (and actually does in Python, but we haven't seen that yet).
> {: .solution}
{: .challenge}

> ## Slicing
>
> What does the following program print?
>
> ~~~
> library_name = 'social sciences'
> print('library_name[1:3] is:', library_name[1:3])
> ~~~
> {: .python}
> ~~~
> library_name[1:3] is: oc
> ~~~
> {: .output}
>
> We can also use variables as our slicing indices. For example if we had ,
> numbers: `low = 3`, `high = 8` and `negative = -1`
> 1.  What does `library_name[low:high]` do?
> 2.  What does `library_name[low:]` (without a value after the colon) do?
> 3.  What does `library_name[:high]` (without a value before the colon) do?
> 4.  What does `library_name[:]` (just a colon) do?
> 5.  What does `library_name[low:negative]` do?
>
> > ## Solution
> > 1. ial s  
> > 2. ial sciences  
> > 3. social s  
> > 4. social sciences  
> > 5. ial science  
> {: .solution}
{: .challenge}
