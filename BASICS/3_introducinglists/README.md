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
    ```bash
    >>> bicycles = ['trek','cannondale','redline','specialized']
    >>> print(bicycles)
    ['trek', 'cannondale', 'redline', 'specialized']
    ```
- You dont want users to see the brackets and quotes. So we access each elements in a list.

#### Accessingg Elements in a list:
    ```bash
    >>> print(bicycles[0])
    trek

    # Formatting:
    >>> print(bicycles[0].title())
    Trek

    >>> print(type(bicycles[0]))     
    <class 'str'>
    ```
#### Index Positions Start at 0, Not 1:

    ```bash
    >>> print(f"{bicycles[0]} is the 1st item \"bicycle[0]\"")
    trek is the 1st item "bicycle[0]"
    ```
- Indexing last elements with -1. 
    ```bash
    >>> print(bicycles[-1])
    specialized
    ```
- -2 => second last, -3 third item from the last of the list.
#### Using Individual Values From a list:

    ```bash
    >>> print(f'hello ! {bicycles[0]} bicycle owner')
    hello ! trek bicycle owner
    >>> message = f'hello ! {bicycles[0].title()} bicycle owner'
    >>> print(message)
    hello ! Trek bicycle owner
    ```
#### Try it yourself:

- 3.1 Names:
    ```bash
    >>> names = ['John', 'Will', 'Charlie', 'Bob']   
    >>> print(names[0],names[1],names[2],names[3])
    John Will Charlie Bob
    ```
- 3.2 Greetings:
    ```bash
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
Most lists you create will be dynamic, meaning you’ll build a list and then add and remove elements from it as your program runs its course. For example, you might create a game in which a player has to shoot aliens out
of the sky. You could store the initial set of aliens in a list and then remove an alien from the list each time one is shot down. Each time a new alien appears on the screen, you add it to the list. Your list of aliens will increase and decrease in length throughout the course of the game.

#### Modifying Elements in a List:

    ```bash
    >>> num = ['1','2','3']
    >>> print(num)
    ['1', '2', '3']
    >>> num[0] = 0
    >>> print(num)
    [0, '2', '3']
    ```
#### Adding elements to a list:

##### Appending Elements to the End of a List:

    ```bash
    >>> motorcycles = ['honda','yamaha','suzuki']
    >>> print(motorcycles)
    ['honda', 'yamaha', 'suzuki']
    >>> motorcycles.append('ducati')
    >>> print(motorcycles)
    ['honda', 'yamaha', 'suzuki', 'ducati']
    ```
- The append() method adds 'ducati' to the end of the list without affecting any of the other elements in the list. You could start with an empty list ``` motorcycles = [] ``` and append dynamically on it. 

##### Inserting Elements into a list:
- The insert() method opens a space at position 0 and stores the value 'ducati' at that location. This operation shifts every other value in the list one position to the right.
    ```bash
    >>> motorcycles
    ['honda', 'yamaha', 'suzuki', 'ducati']
    >>> motorcycles.insert(0,'TVS')
    >>> motorcycles
    ['TVS', 'honda', 'yamaha', 'suzuki', 'ducati']
    ```
#### Removing Elements from a List:
##### Removing an item using the del statement:
    ```bash
    >>> motorcycles
    ['TVS', 'honda', 'yamaha', 'suzuki', 'ducati']
    >>> del motorcycles[0]
    >>> motorcycles        
    ['honda', 'yamaha', 'suzuki', 'ducati']
    ```
- You have to know the index of an item you want to delete from the list.
##### Removing an item using the pop() method:
- pop() returns the value it removed
- It removes the last item in a list. 
    ```bash
    >>> motorcycles
    ['honda', 'yamaha', 'suzuki', 'ducati']
    >>> popped_motorcycle = motorcycles.pop()
    >>> motorcycles
    ['honda', 'yamaha', 'suzuki']
    >>> popped_motorcycle
    'ducati'

    # Application of a pop()
    >>> first_owned = motorcycles.pop(0)
    >>> print(f"The first motorcycle I owned was a {first_owned.title()}")
    The first motorcycle I owned was a Honda
    ```

when you want to delete an item from a list and not use that item in any way, use the del statement; if you want to use an item as you remove it, use the pop() method.

##### Removing an item by value:
- use remove() method
    ```bash
    >>> motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
    >>> motorcycles.remove('ducati')
    >>> motorcycles
    ['honda', 'yamaha', 'suzuki']
    ```
- ```motorcycles.remove('ducati')``` figures out where 'ducati' is in the list and removes that element.
    ```bash
    # Reason for removing : Too expensive
    >>> motorcycles = ['honda', 'yamaha', 'suzuki', 'ducati']
    >>> too_expensive = 'ducati'
    >>> motorcycles.remove('ducati')
    >>> motorcycles
    ['honda', 'yamaha', 'suzuki']
    >>> print(f"\nA {too_expensive.title()} is too expensive for me.")
    A Ducati is too expensive for me.
    ``` 
- *NOTE: The remove() methods deletes only the first occurrence of the value you specify. If there's a possibility the value appears more than once in the list,you'll need to use a loop.*
