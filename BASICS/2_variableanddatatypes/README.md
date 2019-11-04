## Chapter 2 : Variables and simple data types
---

In this chapter you will learn to work with *variables*. You will learn to use descriptive *variable names* and how to *resolve name errors* and *syntax errors* when they arise. You will learn what *strings* are and how to display strings using *lowercase, uppercase, and title case*. You will start using whitespace to organize output neatly, and you will learn to strip unneeded whitespace from different parts of a string. You will start working with integers and floats, and learn some of the ways you can work with numerical data. You will also learn to write explanatory comments to make your code easier for you and others to read. Finally, you will read about the philosophy of keeping your code as simple as possible, whenever possible Python Shell workout and some snippets in chapter2.py.

### Topics Covered:
1. Naming
2. Strings
3. Numbers
4. Comments
5. The Zen of Python
---

### Hello world program:
- ```message``` is a variable and ```Hello python world !``` is the value of ```message``` variable


    ```bash
        >>> message = "Hello python world!" 
        >>> print(message)
        Hello python world!
    ```
---
### 1. Naming Conventions:
#### Name : 
- Letters, numbers, underscore. 
- Starts with letters or number. 
- No space, keywords
- short and descriptive
- lowercase l and 1 and uppercase O and 0 are confusing, beware of those
- lowercase names, uppercase -> classes and constants
#### Name Errors: 
- Purposeful error while running follwing script

    ```python
        message = "Hello Python Crash Course world!"

        print(meas)
    ```
- Output: 
    ```bash 
        Traceback (most recent call last):
        File "chapter2.py", line 9, in <module>
            print(meas)
        NameError: name 'meas' is not defined
    ```
- Traceback is a record of where the interpreter ran into trouble
- file name ```chapter2.py``` has error at line 9. 
- NameError occurred and ```meas``` is not defined.
- A name error usually means we either forgot to set a variable’s value before using it, or we made a spelling mistake when entering the variable’s name.
---
### 2. Strings:
- Series of character
- inside quotes (both single and double) 
    ```python

        string1 = "I'm string"
        string2 = ' "I am also string", said string 2'
    ```
    - Note the use of ' in " and vice versa without escape sequence.
    ```bash

        >>> message = "One of Python's strengths is its diverse community."
        >>> print(message)
        One of Python's strengths is its diverse community.
    ```
#### Changing cases:

    ```bash
        #title function to capitalize initials
        >>> name = "ada lovelace"
        >>> print(name.title())
        Ada Lovelace

        # change a string to all uppercase or all lowercase:

        >>> name = "Ada Lovelace"
        >>> print(name.upper())
        ADA LOVELACE
        >>> print(name.lower())
        ada lovelace     
    ```
- The lower() method is particularly useful for storing data. Many times you won’t want to trust the capitalization that your users provide, so you’ll convert strings to lowercase before storing them
#### Using Variables in strings:
- Combining two strings:
    ```python
        first_name = "ada"
        last_name = "lovelace"
        full_name = f"{first_name} {last_name}"
        message = f"Hello, {full_name.title()}!"
        print(message)
        # o/p : Hello, Ada Lovelace!
    ```
    - To insert a variable’s value into a string, place the letter **f** immediately before the opening quotation mark. Put braces around the name or names of any variable you want to use inside the string. Python will replace each variable with its value when the string is displayed. These strings are called f-strings. The f is for format, because Python formats the string by replacing the name of any variable in braces with its value.
    - Tryouts:
        ```bash

            >>> a = "apple"
            >>> i = "iphone"
            >>> formatted = f"{a}'s {i}"
            >>> formatted
            "apple's iphone"

            # Another Variant
            >>> first_name = "ada"
            >>> last_name = "lovelace"
            >>> full_name = f"{first_name} {last_name}"
            >>> print(f"Hello, {full_name.title()}!")   
            Hello, Ada Lovelace
            # Assign entire message to a variable
            >>> message = f"Hello, {full_name.title()}!"
            >>> print(message)
            Hello, Ada Lovelace!

            # f string present in python >= 3.6)
            # other version uses format() method. 
            >>> full_name = "{} {}".format(first_name, last_name)
            >>> full_name
            'ada lovelace'
        ```
#### Whitespaces in Strings:
- Whitespace refers to any nonprinting character such as spaces, tabs, end of line symbols. 
- Adding Whitespaces
    ```bash

        #Adding tabs:
        >>> print("a \t b \t cdefgh")
        a        b       cdefgh

        #Adding newlines:
        >>> print("1. one\n2. Two\n3. Three")   
        1. one
        2. Two
        3. Three

        # Combine tabs and new lines:
        >>> print("1.\tone\n2.\tTwo\n3.\t^SThree")
        1.      one
        2.      Two
        3.      Three



    ```
- Stripping Whitespaces:
    - We can eliminate extraneous whitespace. Which makes comparison easy. We must often treat 'python ' and 'python' sort of strings as the same. 
    - To ensure that no whitespace exists at the right end of a string, use the rstrip() method.

    ```bash

        >>> favorite_language
        'python '
        >>> favorite_language.rstrip()
        'python'
        >>> favorite_language
        'python '

        # To remove the whitespace from the 
        # string permanently, you have to 
        # associate the stripped value with the variable name:
        >>> favorite_language = favorite_language.rstrip()
        >>> favorite_language
        'python'

        # You can also strip whitespace from the left
        # side of a string using the lstrip() method, 
        # or from both sides at once using strip():

        >>> favorite_language = ' python '
        >>> favorite_language.lstrip()
        'python '
        >>> favorite_language.strip()
        'python'

    ```
    - In the real world, these stripping functions are used most often to clean up user input before it’s stored in a program.
#### Avoiding Syntax Errors with strings:
- A syntax error occurs when Python doesn’t recognize a section of your program as valid Python code. For example, if you use an apostrophe within single quotes, you’ll produce an error. This happens because Python interprets everything between the first single quote and the apostrophe as a string. It then tries to interpret the rest of the text as Python code, which causes error.
    ```bash

    >>> message = "One of python's strengths is its diverse community"
    >>> print(message)
    One of python's strengths is its diverse community


    >>> print('one of python's strength is its diverse community')
    File "<stdin>", line 1
        print('one of python's strength is its diverse community') 
                            ^
    SyntaxError: invalid syntax

    ```
- Error debugging suggestion in Appendix C
#### Try it yourself:
- 2.3 Personal Message:
    ```bash
    >>> name = "V-Ten"
    >>> message = f"Hello {name} would you like to learn python today"
    >>> print(message)
    HelloV-Ten would you like to learn python today
    ```
- 2.4 Name Cases:

    ```bash

    >>> name = 'saMIr gHisING'
    >>> lower = name.lower()
    >>> upper = name.upper()
    >>> title = name.title()
    >>> print(f"lower: {lower}\nupper: {upper}\ntitle: {title}")
    lower: samir ghising
    upper: SAMIR GHISING
    title: Samir Ghising

    ```
- 2.5 Famous Quote:

    ```bash

    >>> author = "Psalm"
    >>> quote = "Search in your own heart with all diligence because out of it flow the issue of life"
    >>> print(f"{author} once said, \"{quote}\"")
    Psalm once said, "Search in your own heart with all diligence because out of it flow the issue of life"

    ```
- 2.6 Strippingg:

    ```bash

    # lstrip() and rstrip() can also be done 
    >>> name = "\tJohn \t Cena\t"
    >>> print(name)         
            John     Cena   
    >>> print(name.strip())
    John     Cena

    ```
---
### 3. Numbers:
#### Integers:
- Operators : +, -, /, *, **, %
- Orders : Priorities; (PEMDAS)
#### Floats:
- Numbers with Decimals points
- Weird stuffs:
    ```bash
    >>> 0.2 + 0.1
    0.30000000000000004
    ```
- Division's result is floats even if dividend and divisor are integers:
    ```bash
    >>> 4/2
    2.0
    ```
- mixing integers and floats gives floats.
    ```bash
    >>> 1 + 2.0
    3.0
    ```
#### Underscores in Numbers:
- For grouping of long Numbers:
    ```bash
    >>> universeAge = 14_000_000_000
    >>> universeAge
    14000000000
    >>> ram = 10_00_00
    >>> ram
    100000
    ```
- Not necessarily digit limit or comma's grouping convention. 
#### Multiple Assignments:
- Separate variable names with commas you can do the usual assignment after that. 
    ```bash
    >>> x, y, z = 0,1,2
    >>> print(f"{x}{y}{z}")
    012
    >>> print(x,y,z)
    0 1 2
    ```
#### Constants:
- Python doesn’t have built-in constant types, but Python programmers use all capital letters to indicate a variable should be treated as a constant and never be changed:
    ```bash
    >>> MAX = 20000
    ```
#### Try it yourself:
- 2.8 Number Eight:
    ```bash
    >>> print(5+3)
    8
    >>> print(11-3)
    8
    >>> print(8*1)
    8
    >>> print(16/2)
    8.0
    ```
- 2.9 Favorite Number:
    ```bash
    >>> favorite_number = 42
    >>> message = "My favorite number is:" 
    >>> print(message, favorite_number)
    My favorite number is: 42
    ```
---
### 4. Comments:
- '#' indicates comment
    ```python
    # This is comment 
    ```
- Python iggnores comments.
---
### 5. THE ZEN OF PYTHON

```

    >>> import this
    The Zen of Python, by Tim Peters

    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.   
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!

```
#### Beautiful is better than ugly.

- Programmers have always respected well-designed efficient, and even beautiful solutions to problems.

#### Simple is better than complex.
- If you have a choice between a simple and a complex solution, and both work, use the simple solution. Your code will be easier to maintain, and it will be easier for you and others to build on that code later on.

#### Complex is better than complicated.
- Real life is messy, and sometimes a simple solution to a problem is
unattainable. In that case, use the simplest solution that works.

#### Readability counts.
- When you’re working on a project that involves complex coding, focus on writing informative comments for that code.

#### There should be one-- and preferably only one --obvious way to do it.
- The nuts and bolts of your programs should make sense to other Python programmers.

#### Now is better than never.
- You could spend the rest of your life learning all the intricacies of Python and of programming in general, but then you’d never complete any projects. Don’t try to write perfect code; write code that works, and then decide whether to improve your code for that project or move on to something new.