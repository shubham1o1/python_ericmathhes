## Chapter 2 : Variables and simple data types
---

- Python Shell workout and some snippets in chapter2.py are present here.

### Hello world program:
- ```message``` is a variable and ```Hello python world !``` is the value of ```message``` variable


    ```bash
        >>> message = "Hello python world!" 
        >>> print(message)
        Hello python world!
    ```
### Naming Conventions:
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
### Strings:
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

    ```
