# Chapter 3 : Introducing Lists 

In this chapter you will learn what lists are and how to work with the individual items in a list. You will learn how to define a list and how to add and remove elements. You learned to sort lists permanently and temporarily for display purposes. You also learned how to find the length of a list and how to avoid index errors when you’re working with lists. In Chapter 4 you’ll learn how to work with items in a list more efficiently. By looping through each item in a list using just a few lines of code you’ll be able to work efficiently, even when your list contains thousands or millions of items.

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
#### TIY:
##### 3-4. Guest List: 
If you could invite anyone, living or deceased, to dinner, who would you invite? Make a list that includes at least three people you’d like to
invite to dinner. Then use your list to print a message to each person, inviting
them to dinner.
    ```bash
    >>> invitiation_lists
    ['John Cena', 'The Rock', 'The Undertaker', 'The Big Show']
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[0]}")
    I'd like to invite you for dinner Mr. John Cena
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[1]}")
    I'd like to invite you for dinner Mr. The Rock
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[2]}")
    I'd like to invite you for dinner Mr. The Undertaker
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[3]}")
    I'd like to invite you for dinner Mr. The Big Show
    ```
##### 3-5. Changing Guest List: 
You just heard that one of your guests can’t make the dinner, so you need to send out a new set of invitations. You’ll have to think of
someone else to invite.
- Start with your program from Exercise 3-4. Add a print() call at the end
of your program stating the name of the guest who can’t make it.
- Modify your list, replacing the name of the guest who can’t make it with
the name of the new person you are inviting.
- Print a second set of invitation messages, one for each person who is still
in your list.
    ```bash
    >>> print(invitiation_lists[1])
    The Rock
    >>> invitiation_lists[1] = 'Stone Cold'
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[0]}")
    I'd like to invite you for dinner Mr. John Cena
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[1]}")
    I'd like to invite you for dinner Mr. Stone Cold
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[2]}")
    I'd like to invite you for dinner Mr. The Undertaker
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[3]}")
    I'd like to invite you for dinner Mr. The Big Show
    ```
##### 3-6. More Guests: 
You just found a bigger dinner table, so now more space is available. Think of three more guests to invite to dinner.
- Start with your program from Exercise 3-4 or Exercise 3-5. Add a print() call to the end of your program informing people that you found a bigger dinner table.
- Use insert() to add one new guest to the beginning of your list.
- Use insert() to add one new guest to the middle of your list.
- Use append() to add one new guest to the end of your list.
- Print a new set of invitation messages, one for each person in your list.
    ```python
    >>> invitiation_lists.insert(0,'Hulk Hogan')
    >>> invitiation_lists.insert(3,'Shawn Michaels')
    >>> invitiation_lists.append('Triple H')
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[0]}")
    I'd like to invite you for dinner Mr. Hulk Hogan
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[1]}")
    I'd like to invite you for dinner Mr. John Cena
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[2]}")
    I'd like to invite you for dinner Mr. Stone Cold
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[3]}")
    I'd like to invite you for dinner Mr. Shawn Michaels
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[4]}")
    I'd like to invite you for dinner Mr. The Undertaker
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[5]}")
    I'd like to invite you for dinner Mr. The Big Show
    >>> print(f"I'd like to invite you for dinner Mr. {invitiation_lists[6]}")
    I'd like to invite you for dinner Mr. Triple H
    ```
##### 3-7. Shrinking Guest List
You just found out that your new dinner table won’t arrive in time for the dinner, and you have space for only two guests.
- Start with your program from Exercise 3-6. Add a new line that prints a message saying that you can invite only two people for dinner.
- Use pop() to remove guests from your list one at a time until only two names remain in your list. Each time you pop a name from your list, print a message to that person letting them know you’re sorry you can’t invite them to dinner.
- Print a message to each of the two people still on your list, letting them know they’re still invited.
- Use del to remove the last two names from your list, so you have an empty list. Print your list to make sure you actually have an empty list at the end of your program.
    ```python
    >>> message = 'Sorry your invitation has been cancelled'
    >>> print(f"{message} {invitiation_lists.pop()}")
    Sorry your invitation has been cancelled Triple H
    >>> print(f"{message} {invitiation_lists.pop()}")
    Sorry your invitation has been cancelled The Big Show
    >>> print(f"{message} {invitiation_lists.pop()}")
    Sorry your invitation has been cancelled The Undertaker
    >>> print(f"{message} {invitiation_lists.pop()}")
    Sorry your invitation has been cancelled Shawn Michaels
    >>> print(f"{message} {invitiation_lists.pop()}")
    Sorry your invitation has been cancelled Stone Cold
    >>> message = "you are still invited"
    >>> print(f"{message} {invitiation_lists[0]}")    
    you are still invited Hulk Hogan
    >>> print(f"{message} {invitiation_lists[1]}") 
    you are still invited John Cena
    >>> del invitiation_lists[0]
    >>> del invitiation_lists[0] 
    >>> invitiation_lists
    []
    ```

---

### Organizing a List:
Often, your lists will be created in an unpredictable order, because you can’t always control the order in which your users provide their data. Although this is unavoidable in most circumstances, you’ll frequently want to present your information in a particular order. Sometimes you’ll want to preserve the original order of your list, and other times you’ll want to change the original order. Python provides a number of different ways to organize your lists, depending on the situation

#### Sorting a List Permanently with the sort() method:
- We can use the **sort()** method.
- Alphabetical Sort:
    ```python
    >>> cars = ['bmw', 'audi', 'toyota', 'subaru']
    >>> cars.sort()
    >>> print(cars)
    ['audi', 'bmw', 'subaru', 'toyota']
    ```
- The sort() method, shown at u, changes the order of the list permanently. The cars are now in alphabetical order, and we can never revert to the original order
- You can also sort this list in reverse alphabetical order by passing the argument reverse=True to the sort() method.
    ```python
    >>> cars.sort(reverse=True)
    >>> print(cars)
    ['toyota', 'subaru', 'bmw', 'audi']
    ```
#### Sorting a List Temporarily with the sorted() Function:
- The **sorted()** function lets you display your list
in a particular order but doesn’t affect the actual order of the list.
    ```python
    >>> cars = ['bmw', 'audi', 'toyota', 'subaru']
    >>> print("Here is the original list:")
    Here is the original list:
    >>> cars
    ['bmw', 'audi', 'toyota', 'subaru']
    >>> print("\nHere is the sorted list:")
    Here is the sorted list:
    >>> print(sorted(cars))
    ['audi', 'bmw', 'subaru', 'toyota']
    >>> print("Here is the original list again:")
    Here is the original list again:
    >>> print(cars)
    ['bmw', 'audi', 'toyota', 'subaru']
    ```
- The sorted() function can also accept a reverse=True
*NOTE: Sorting a list alphabetically is a bit more complicated when all the values are not in lowercase. There are several ways to interpret capital letters when determining a sort order, and specifying the exact order can be more complex than we want to deal with at this time. However, most approaches to sorting will build directly on what you learned in this section.*

#### Printing a List in Reverse Order:
- To reverse the original order of a list, you can use the reverse() method.
    ```python
    >>> cars
    ['bmw', 'audi', 'toyota', 'subaru']
    >>> cars.reverse()
    >>> print(cars)
    ['subaru', 'toyota', 'audi', 'bmw']
    >>> cars.reverse()
    >>> print(cars)    
    ['bmw', 'audi', 'toyota', 'subaru']
    ```
- The reverse() method changes the order of a list permanently, but you can revert to the original order anytime by applying reverse() to the same list a second time.

#### Finding the length of a List:
- You can quickly find the length of a list by using the len() function
    ```bash
    >>> cars
    ['bmw', 'audi', 'toyota', 'subaru']
    >>> len(cars)
    4
    ```
*NOTE: Python counts the items in a list starting with one, so you shouldn’t run into any offby-one errors when determining the length of a list.*

#### TIY
##### 3-8. Seeing the World: 
Think of at least five places in the world you’d like to
visit.
- Store the locations in a list. Make sure the list is not in alphabetical order.
- Print your list in its original order. Don’t worry about printing the list neatly, just print it as a raw Python list.
- Use sorted() to print your list in alphabetical order without modifying the actual list.
- Show that your list is still in its original order by printing it.
- Use sorted() to print your list in reverse alphabetical order without changing the order of the original list.
- Show that your list is still in its original order by printing it again.
- Use reverse() to change the order of your list. Print the list to show that its order has changed.
- Use reverse() to change the order of your list again. Print the list to show it’s back to its original order.
- Use sort() to change your list so it’s stored in alphabetical order. Print the list to show that its order has been changed.
- Use sort() to change your list so it’s stored in reverse alphabetical order. Print the list to show that its order has changed.
    ```python
    >>> places = ['Amazon','Norway','Grand Canyon','Bali','Beijing']
    >>> print(places)
    ['Amazon', 'Norway', 'Grand Canyon', 'Bali', 'Beijing']
    >>> print(sorted(places))
    ['Amazon', 'Bali', 'Beijing', 'Grand Canyon', 'Norway']
    >>> print(places)
    ['Amazon', 'Norway', 'Grand Canyon', 'Bali', 'Beijing']
    >>> print(sorted(places, reverse=True))
    ['Norway', 'Grand Canyon', 'Beijing', 'Bali', 'Amazon']
    >>> print(places)
    ['Amazon', 'Norway', 'Grand Canyon', 'Bali', 'Beijing']
    >>> places.reverse()
    >>> print(places)    
    ['Beijing', 'Bali', 'Grand Canyon', 'Norway', 'Amazon']
    >>> places.reverse()
    >>> print(places)    
    ['Amazon', 'Norway', 'Grand Canyon', 'Bali', 'Beijing']
    >>> places.sort()
    >>> print(places) 
    ['Amazon', 'Bali', 'Beijing', 'Grand Canyon', 'Norway']
    >>> places.sort(reverse=True)
    >>> print(places)
    ['Norway', 'Grand Canyon', 'Beijing', 'Bali', 'Amazon']
    ```
##### 3-9. Dinner Guests
Working with one of the programs from Exercises 3-4
through 3-7 (page 42), use len() to print a message indicating the number of people you are inviting to dinner.
    ```python
    >>> invitiation_lists = ['John','hulk','undertaker','rock','bigshoow']
    >>> print(f"the number of guests are {len(invitiation_lists)}")
    the number of guests are 5
    ```
##### 3-10. Every Function: 
Think of something you could store in a list. For example, you could make a list of mountains, rivers, countries, cities, languages, or anything else you’d like. Write a program that creates a list containing these items and then uses each function introduced in this chapter at least once.
    ```python
    >>> rivers = ['Deonia','koshi','mechi','adhuwa khola','kankai']
    >>> print(sorted(rivers))
    ['Deonia', 'adhuwa khola', 'kankai', 'koshi', 'mechi']
    >>> print(len(rivers))    
    5
    >>> rivers.sort()      
    >>> print(rivers)
    ['Deonia', 'adhuwa khola', 'kankai', 'koshi', 'mechi']
    ```

---

### Avoiding Index Errors When working with Lists:
- Accessing 4th item of a list with 3 items
    ```python
    >>> motorcycles = ['honda', 'yamaha', 'suzuki']
    >>> print(motorcycles[3])
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    IndexError: list index out of range
    ```
- An index error means Python can’t find an item at the index you requested. If an index error occurs in your program, try adjusting the index you’re asking for by one
- Accessing last item in the list with **-1** index.
    ```python
    >>> motorcycles = ['honda', 'yamaha', 'suzuki']
    >>> print(motorcycles[-1])
    suzuki
    ```
- Accessing last item of an empty list:
    ```python
    >>> empty_list = []
    >>> print(empty_list[-1]) 
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    IndexError: list index out of range
    ```
*NOTE: If an index error occurs and you can’t figure out how to resolve it, try printing your list or just printing the length of your list. Your list might look much different than you thought it did, especially if it has been managed dynamically by your program. Seeing the actual list, or the exact number of items in your list, can help you sort out such logical errors.*

#### TIY:

##### 3-11. Intentional Error
If you haven’t received an index error in one of your programs yet, try to make one happen. Change an index in one of your programs to produce an index error. Make sure you correct the error before closing the program.

    ```python
    >>> vowels = ['a','e','i','o','u']
    >>> print(vowels[5])
    Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
    IndexError: list index out of range
    >>> print(vowels[-1])
    u
    >>> print(vowels[-4]) 
    e
    ```

------------------EOC------------------