## Chapter 2 : Variables and simple data types
---

### Hello world program:
- ```message``` is a variable and ```Hello python world !``` is the value of ```message``` variable


    ```bash
        >>> message = "Hello python world!" 
        >>> print(message)
        Hello python world!
    ```

### Naming Conventions:
- #### Name : 
    - Letters, numbers, underscore. 
    - Starts with letters or number. 
    - No space, keywords
    - short and descriptive
    - lowercase l and 1 and uppercase O and 0 are confusing, beware of those
    - lowercase names, uppercase -> classes and constants
- #### Name Errors: 
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
- #### Changing cases:
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
- #### Using Variables in strings:
- Combining two strings:
    ```python
        first_name = "ada"
        last_name = "lovelace"
        full_name = f"{first_name} {last_name}"
        message = f"Hello, {full_name.title()}!"
        print(message)
        # o/p : Hello, Ada Lovelace!
    ```
    - To insert a variable’s value into a string, place the letter **f** immediately before the opening quotation mark. Put braces around the name or names of any variable you want to use inside the string. Python will replace each variable with its value when the string is displayed. These strings are called f-strings. The f is for format, because Python formats the string by replacing the name of any variable in braces with its
    value.