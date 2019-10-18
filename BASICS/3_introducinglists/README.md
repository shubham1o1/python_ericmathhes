# Chapter 3 : Introducing Lists 

--Intro--

## Brief Content Overview: 
1. What is List? 
2. Changing, Adding, and Removingg Elements 
3. Organizing a List
4. Avoiding Index Errors 

---

### 1 What is List
- Collection of items in a particular order.
- Good Convention : Variable name is plural
- Represented by the square bracket []
- Can contain anything (heterogenous or homogenous elements)
    ```shell
    >>> bicycles = ['trek','cannondale','redline','specialized']
    >>> print(bicycles)
    ['trek', 'cannondale', 'redline', 'specialized']
    ```
- You dont want users to see the brackets and quotes. So we access each elements in a list.

#### Accessingg Elements in a list:
    ```shell
    >>> print(bicycles[0])
    trek

    # Formatting:
    >>> print(bicycles[0].title())
    Trek

    >>> print(type(bicycles[0]))     
    <class 'str'>
    ```
#### Index Positions Start at 0, Not 1:

    ```shell
    >>> print(f"{bicycles[0]} is the 1st item \"bicycle[0]\"")
    trek is the 1st item "bicycle[0]"
    ```
- Indexing last elements with -1. 
    ```shell
    >>> print(bicycles[-1])
    specialized
    ```
- -2 => second last, -3 third item from the last of the list.
#### Using Individual Values From a list:
    ```shell
    >>> print(f'hello ! {bicycles[0]} bicycle owner')
    hello ! trek bicycle owner
    >>> message = f'hello ! {bicycles[0].title()} bicycle owner'
    >>> print(message)
    hello ! Trek bicycle owner
    ```
#### Try it yourself:

- 3.1 Names:
    ```shell
    >>> names = ['John', 'Will', 'Charlie', 'Bob']   
    >>> print(names[0],names[1],names[2],names[3])
    John Will Charlie Bob
    ```
- 3.2 Greetings:
    ```shell
    >>> message = "Hello! my friend"   
    >>> print(f'{message} names[0]')
    Hello! my friend names[0]
    >>> print(f'{message} {names[0]}')
    Hello! my friend John
    >>> print(f'{message} {names[1]}') 
    Hello! my friend Will
    >>> print(f'{message} {names[2]}') 
    Hello! my friend Charlie
    >>> print(f'{message} {names[3]}') 
    Hello! my friend Bob

    >>> print(f'{message} {names[4]}') 
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    IndexError: list index out of range

    ```
---
### 2 Changing, Adding, and Removing Elements:
