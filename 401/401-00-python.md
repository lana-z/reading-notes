### Jan 04, 2024

## 401 Prep Notes
### Source: [Learn Microsoft Python for beginners](https://learn.microsoft.com/en-us/training/modules/python-create-manage-projects/2-set-up-project)


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
- 3) f strings
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


## Things I want to learn more about
Refresher from 301 - what are expressions?

Source: chatGPT

```subject = "interesting facts about the moon"
heading = f"{subject.title()}"
print(heading)
```

The expression is subject.title(). An expression is a combination of values, variables, operators, and calls to functions that are evaluated to a single value. In this case, subject.title() is an expression that calls the .title() method on the string variable subject. This method returns a new string where the first character of each word is capitalized.

The expression is used inside a formatted string literal (denoted by the f before the quotation marks), which allows for embedding expressions inside string literals. The entire f"{subject.title()}" is a formatted string literal, and within the curly braces {}, the subject.title() is the expression that gets evaluated and included in the resulting string.
