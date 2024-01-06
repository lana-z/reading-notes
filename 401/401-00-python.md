### Jan 04, 2024

## 401 Prep Notes

### Source: [Microsoft Learn Python for beginners](https://learn.microsoft.com/en-us/training/modules/python-create-manage-projects/2-set-up-project)

Note that I use direct quotes from the course curriculum throughout this file.

## Corresponding Sandbox Repo on Github
I created [this repo](https://github.com/lana-z/microsoft-learn-python) as a sandbox for my Microsoft Learn Python for beginners course.

#### Boolean logic in python
- In Python, None and 0 are also interpreted as False.
- Equals: a == b
- Not Equals: a != b
- Less than: a < b
- Less than or equal to: a <= b
- Greater than: a > b
- Greater than or equal to: a >= b
Syntax of if

```
a = 93
b = 27
if a >= b:
    print(a)
```
Output : 93

In Python, the body of an if statement must be indented.



- new keyword statement else if is `elif`

```
if condition1:
    # Code to execute if condition1 is true
elif condition2:
    # Code to execute if condition1 is false but condition2 is true
else:
    # Code to execute if both condition1 and condition2 are false
```
Can also nest logic
```
if test_expression:
    # statement(s) to be run
    if test_expression:
        # statement(s) to be run
    else:
        # statement(s) to be run
elif test_expression:
    # statement(s) to be run
    if test_expression:
        # statement(s) to be run
    else:
        # statement(s) to be run
else:
    # statement(s) to be run
```



#### Packages

- packages are external modules or libraries that you include in your project that are written by others

- create a virtual environment by calling the `venv` module
  - `python -m venv env`

- activate
  - `source env/bin/activate`

- deactivate
  - `deactivate`

- python -m venv env
- .\env\Scripts\activate

#### Strings
- Operations on strings always produce new strings as a result.
- You can enclose Python strings in single, double, or triple quotation marks. Stick to the one you choose for the project as a best practice.
  - use a different style to enclose substrings.
  - When the text has a combination of single and double quotation marks, you can use triple quotation marks to prevent syntax errors.
- use `\n` or `""" variable value here """` for multiple line single variables
- case sensitive

Three types of formatting
- 1) %
```mass_percentage = "1/6"
print("On the Moon, you would weigh about %s of your weight on Earth." % mass_percentage)
```
- 2) .format() method using {}

```
mass_percentage = "1/6"
print("""You are lighter on the {0}, because on the {0} you would weigh about {1} of your weight on Earth.""".format("Moon", mass_percentage))
```

or
```
mass_percentage = "1/6"
print("""You are lighter on the {moon}, because on the {moon} you would weigh about {mass} of your weight on Earth.""".format(moon="Moon", mass=mass_percentage))
```
- 3) f strings - f stands for formatted string
```
print(f"On the Moon, you would weigh about {mass_percentage} of your weight on Earth.")
```
With f-strings, you don't need to assign a value to a variable beforehand

#### Mathematical operations in python

- // - floor division, rounds down
- % - modulo operator, remainder

Order of operation
1. Parentheses
2. Exponents
3. Multiplication and division
4. Addition and subtraction


It's a best practice to use parentheses even if order of operation would evaluate the same way without them. Example: result_2 = 1032 + (26 * 2) instead of result_1 = 1032 + 26 * 2

Convert strings, for ex from user input, to numbers
- `int` - integer, whole number
- `float` - decimal value

Absolute value
- ex: -23 absolute value is 23
- use `abs`

```
print(abs(39 - 16))
print(abs(16 - 39))
```

> One of the most common is the `math` library.
... Rounding numbers enables you to remove the decimal portion of a float. You can choose to always round up to the nearest whole number by using `ceil`, or down by using `floor`.

#### Lists

- Lists in Python are dynamic: you can add and remove items after they're created. To add an item to a list, use the method .append(value).
- You can remove the last item in a list by calling the .pop() method on the list variable.
- see the Sandbox repo referenced above for using index, min, max and more with lists.

- Note that indexes end before the ending index. Ex:
[0:2] will only list 0 and 1.

- If you don't include the stopping index in the slice, Python assumes that you want to go to the end of the list. Ex: [3:] would list the fourth through the end of the list.

Slice and Join
- `.slice()` and `.join()`
- Create a new list, don't modify the current list

Sort
-`.sort()`
Modifies the current list
- Alphabetical order
- To sort a list in reverse order, call .sort(reverse=True) on the list.


#### While and For loops

While
- use for an unknown number of loops
- The loops examine a Boolean condition and, as long as the condition is true, the code inside the loop will run.

```
user_input = ''

while user_input.lower() != 'done':
    user_input = input('Enter a new value, or done when done')
```

``` python
# Create the variable for user input
user_input = ''
# Create the list to store the values
inputs = []

# The while loop
while user_input.lower() != 'done':
    # Check if there's a value in user_input
    if user_input:
        # Store the value in the list
        inputs.append(user_input)
    # Prompt for a new value
    user_input = input('Enter a new value, or done when done')
```
For

Python has many types that can be looped over. These types are known as iterables.
- use for a known number of loops

To unpack variables named left and right from the list turns

```for left, right in turns:```

#### Python dictionaries
 A dictionary is a collection of key/value pairs, like a group of variables inside of a container.
- Python uses curly braces { } and colon : to denote a dictionary

In the example below, there are two keys: name and moons.
```
planet = {
    'name': 'Earth',
    'moons': 1
}
```
 Each key behaves in a similar way as a variable. They have a unique name and store a value. However, they're contained inside of a single, larger variable, named planet.

Get method ```.get()```

These two are the same:
1. print(planet.get('name'))
2. print(planet['name'])

Although the behavior of get and the square brackets ([ ]) is generally the same for retrieving items, there's one key difference. If a key isn't available, get returns None, and [ ] throws a KeyError.

Update method ```.update()```
These two are also the same:
1. planet.update({'name': 'Makemake'})
2. planet['name'] = 'Makemake'

Key names, like everything else in Python, are case sensitive. As a result, 'name' and 'Name' are seen as two separate keys in a Python dictionary.

Dictionaries can be created inside dictionaries for complex data modeling.

To retrieve values in a nested dictionary, you chain together square brackets, or calls to get.

```print(f'{planet["name"]} polar diameter: {planet["diameter (km)"]["polar"]}')```


Check for a key in a dictionary
- ```if``` 'key' ```in``` 'dictionary':
  - ```else:```


Values()
```
total_rainfall = 0
for value in rainfall.values():
    total_rainfall = total_rainfall + value

print(f'There was {total_rainfall}cm in the last quarter.')
```
Output: There was 10.8cm in the last quarter.


#### Functions
- def - define function
- syntax is ```output =``` for the return (edit: actually, return is also used - see Things I want to learn more about below)
- can reuse functions in python similar to modules in js
- functions can be used as arguments in python

Variable arguments
-  It's common to see *args or *a used as a variable name, you should try to use the same convention throughout a project.
- a tuple refers to a type of data structure in Python that is used to store multiple items. Tuples are ordered, meaning the items have a defined sequence, and they are immutable, meaning once created, the items in a tuple cannot be changed (chatGPT)
- When you use variable arguments, each value is no longer assigned a variable name. All values are now part of the catch-all variable name that uses the asterisk (args in these examples).

Kwargs
- Keyword arguments
```
def variable_length(**kwargs):
    print(kwargs)
```

- variable-length keyword arguments are assigned as a dictionary
```
variable_length(tanks=1, day="Wednesday", pilots=3)
{'tanks': 1, 'day': 'Wednesday', 'pilots': 3}
```

Function Review:
- When a function defines/declares arguments, it cannont be called without arguments.
- A function with only keyword arguments can be called without any arguments. Keyword arguments already define defaults, which allows calling a function without them. If a function has only keyword arguments, there's no need to pass any values.
- A function can define arguments and keyword arguments. As long as arguments come in first, a function can be defined with both.
- A function using variable arguments does not need to pass any argument at all.
- *args, **kwargs
  - Although the placeholder name can change, you must use a single asterisk for variable arguments and double asterisks for variable keyword arguments.

<br>
Functions can require arguments or make them optional.
You can extract reusable code and reuse it in a function.
Variable arguments and variable keyword arguments are useful when you don't know the exact inputs.

#### Python error handling
- Tracebacks -  points to the origin and ending of an unhandled error
- stdin - standard input
- exeption name - the actual error Ex: FileNotFoundError
- use `try` with the `except` keyword

My sandbox code is not working correctly on some of the exercises in this unit (see hello-world repo config.py, config.txt files).

Review:
- path, line number, and exception are the three elements to expect to see in a traceback, although there can be more
- `try` and `except` are the two keywords for handling exceptions
- use `err` in an except block when you want to reuse or inspect an exception youre raising
- the syntax to catch two exceptions in the same except line is `except (ValueError, TypeError):`
- 




## Things I want to learn more about
- When to use return and when to use output

For example, in my sandbox repo,
Why is output used in line 5 and return used in lines 26 and 28?
They are both statements to the user that have to be printed with print().


----
<br>
- More about functions that define arguments verses functions that don't and functions that define keyword arguments. Everything in the Function Review above is a little confusing to me rn.

<br>

Unit 2 of 9 in Basics of Python funtions:
>Functions with no arguments
>>In this case, rocket_parts is the name of the function. That name is followed by the empty parentheses, which indicate that no arguments are needed.

Unit 6 of 9 in Basics of Python functions.

Variable arguments
>Arguments in functions are required. But when you're using variable arguments, the function allows any number of arguments (including 0) to be passed in. The syntax for using variable arguments is prefixing a single asterisk (*) before the argument's name.

----
<br>

- Refresher from 301 - what are expressions?

Source: chatGPT

```subject = "interesting facts about the moon"
heading = f"{subject.title()}"
print(heading)
```

The expression is subject.title(). An expression is a combination of values, variables, operators, and calls to functions that are evaluated to a single value. In this case, subject.title() is an expression that calls the .title() method on the string variable subject. This method returns a new string where the first character of each word is capitalized.

The expression is used inside a formatted string literal (denoted by the f before the quotation marks), which allows for embedding expressions inside string literals. The entire f"{subject.title()}" is a formatted string literal, and within the curly braces {}, the subject.title() is the expression that gets evaluated and included in the resulting string.

------
<br>

- When is something a parameter and when is it an argument?

Source: chatGPT

The terms "parameter" and "argument" are often used interchangeably but they have slightly different meanings in the context of functions:

1. **Parameter**:
    - A parameter is a variable listed as part of the function's definition. It's like a placeholder for the data that the function will operate on. You can think of parameters as the "names" you specify in the function definition.
    - In your example, `value` is a parameter of the function `str_to_bool`. It's a name that refers to the data you'll pass into the function when you call it.

      ```python
      def str_to_bool(value):  # 'value' is a parameter
          # Function implementation
      ```

2. **Argument**:
    - An argument is the actual value or data you pass to the function when you call it. It's the "real" piece of data that fills the parameter's place when the function executes.
    - When you call a function and provide values, those values are the arguments. For example, if you have a function call like `str_to_bool("True")`, the string `"True"` is the argument.

      ```python
      str_to_bool("True")  # "True" is an argument
      ```

In summary, when defining a function, the variables listed are called parameters. When calling a function, the values you provide are called arguments. The arguments are the actual data that gets passed into the function, and they correspond to the function's parameters.
