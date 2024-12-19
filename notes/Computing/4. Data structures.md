## Lists
- Lists are used to store multiple items in a single variable
- They are ordered, mutable and allow duplicate values
- Mutable means that list items can be added, updated and removed
### Creating
- Create a list using square brackets (`[]`) or the `list()` constructor
- List items can be of any data type, and can have different data types
- Lists can also contain sublists, which is known as a nested list
```Python
nums = []
nums = list()
nums = [1,2,3,4,5]
nums list(range(10))
chracters = list("spiderman")
fruits = ["apple", "banana", "orange"]
list1 = ["abc", 34, True, 40, "male"]
list2 = [[1, "apple"], [2, "orange"], [3, "pear"]]
```
### Reading
- List items are indexed and we can refer to them by the index number
- Like strings, the first element has an index of zero, second has an index of 1, etc
- The last element also has an index of -1, second last -2, etc
- List items can also be sliced like strings
```Python
fruits = ["apple", "banana", "cherry", "durian"]
print("1:", fruits[0])
print("2:",fruits[1])
print("3:",fruits[-1])
print("4:",fruits[-2])

print("5:",fruits[1:3])
print("6:",fruits[:3])
print("7:",fruits[1:])
print("8:",fruits[1:-1])
print("9:",fruits[0:4:2])
print("10:",fruits[4: 1: -1])
print("11:",fruits[::-1])
```
```Terminal
1:apple
2:banana
3:durian
4:cherry
5:['banana', 'cherry']
6:['apple', 'banana', 'cherry']
7:['banana', 'cherry', 'durian']
8:['banana', 'cherry']
9:['apple', 'cherry']
10:['durian', 'cherry']
11:['durian', 'cherry', 'banana', 'apple']
```
We can also use a for loop to loop through each item in the list
```python
fruits = ["apple", "banana", "cherry", "durian"]
for i in fruits:
	print(i)
```
```Terminal
apple
banana
cherry
durian
```
### Adding
#### append()
- `append()` appends an element to the end of the list
```Python
num = [1,2,3,4,5]
num.append(6)
print(num)
num.append([7,8,9])
print(num)
```
```Terminal
[1, 2, 3, 4, 5, 6]
[1, 2, 3, 4, 5, 6, [7, 8, 9]]
```
### insert()
- The `insert()` method inserts a value at the specified index
- The specified index becomes the inserted element's index
```python
fruits = ["apple", "banana", "orange"]
fruits.insert(2, "cherry")
print(fruits)
fruits.insert(4, ["dan heng", "blade"])
```
```Terminal
['apple', 'banana', 'cherry', 'orange']
['apple', 'banana', 'cherry', 'orange', ['dan heng', 'blade']]
```
### extend()
- `extend()` takes in elements from another list, modifies the first list and adds the elements at the back
- The argument has to be another list or an error will be raised
```Python
num = [1,2,3,4,5]
num.extend([6,7,8])
print(num)
```
```Terminal
[1, 2, 3, 4, 5, 6, 7, 8]
```
#### Operator
- Two lists can be joined together using the `+`  and `+=` operator
```Python
num = [1,2,3,4,5]
num = num + [6,7,8]
print(num)
num += [9,10]
print(num)
```
```Terminal
[1, 2, 3, 4, 5, 6, 7, 8]
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
- We can also repeat a list multiple times with the `*` operator
```Python
num = [1]
num = num * 3
print(num)
num2 = [2]
num2 *= 3
print(num2)
```
```Terminal
[1, 1, 1]
[2, 2, 2]
```
### Updating
- To update a value in the list, we can use its index value
- This is because lists are mutable
```Python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits[1] = 'blackcurrant'
print(fruits)
```
```Terminal
['apple', 'blackcurrant', 'cherry', 'durian']
```
- We can update more than one item by specifying a range of index numbers where you want to insert the new items
```Python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits[1:3] = ['dan heng', 'blade']
print(fruits)
```
```Terminal
['apple', 'dan heng', 'blade', 'durian']
```
- If you insert more/ lesser items than you replace/ update, the new times will be inserted where you specified, and the reminding items will move accordingly
```Python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits[1:3] = ['dan heng', 'stelle', 'march 7th']
print(fruits)
```
```Terminal
['apple', 'dan heng', 'stelle', 'march 7th', 'durian']
```
```Python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits[1:3] = ['dan heng']
print(fruits)
```
```Terminal
['apple', 'dan heng', 'durian']
```
### Deleting
#### remove()
- `remove()` will remove an item based on its value
```Python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits.remove("apple")
print(fruits)
```
```Terminal
['banana', 'cherry', 'durian']
```
- If there are multiple items of the same value, it will only remove the first item
- It will raise an error if the value is not in the list
- `remove()` does not return the removed value
```Python
fruits = ['apple', 'banana', 'cherry', 'durian', "apple"]
fruits.remove("apple")
print(fruits)
```
```Terminal
['banana', 'cherry', 'durian', 'apple']
```
#### pop()
- The `pop()` method removes the element at the specified position
- If no position is specified, the last item is removed by default
- `pop()` returns the value that was removed
```python
num = [1,2,3,4,5]
num.pop()
print(num)

x = num.pop(1)
print(num)
print(x)
```
```Terminal
[1, 2, 3, 4]
[1, 3, 4]
2
```
#### del
- The `del` keyword is used to delete objects
```Python
num = [1,2,3,4,5]
del num[2]
print(num)
del num
print(num) #error, becuase del deleted the whole num list
```
```Terminal
[1, 2, 4, 5]
NameError: name 'num' is not defined
```
#### clear()
- To clear all elements in a lis, use the `clear()` method
```Python
num = [1,2,3]
num.clear()
print(num)
```
```Termnial
[]
```
### Methods
#### min(), max(), sum()
- If the list contains of all integer elements, `min()`, `max()` and `sum()` gives the minimum item, maximum item and the total sum value of the list
```Python
num = [0,1,2,3,4,5,6,7,8,9]
print(min(num))
print(max(num))
print(sum(num))
```
```Terminal
0
9
45
```
- For a list of strings, `min()` and `max` will return the string with the lowest and highest ASCII value
- Lowercase characters have a higher ASCII value than their uppercase counterparts
- Alphabetical order
```python
array = ["raiden", "xiao", "alhitham", "Alhaitham"]
print(min(array))
print(max(array))
```
```Terminal
Alhaitham
xiao
```
#### reverse() and reversed()
- `reverse()` edits the original list and reverses it
- It does not return anything
```Python
nums = [1,2,3]
x= nums.reverse()
print(nums)
print(x)
```
```Terminal
[3, 2, 1]
None
```
- `reversed()` reverses the original list and returns it
```Python
nums = [1,2,3]
x = reversed(nums)
print(nums)
print(x)
print(list(x))
```
```Terminal
[1, 2, 3]
<list_reverseiterator object at 0x102eeee90>
[3, 2, 1]
```
#### sort() and sorted()
- `sort()` edits the original list and sorts it, and does not return anything
- It can take an optional `reverse` parameter
```python
nums = [2,3,1]
x = nums.sort()
print(nums)
print(x)
y = nums.sort(reverse=True)
print(nums)
print(y)
```
```Terminal
[1, 2, 3]
None
[3, 2, 1]
None
```
- `sorted()` sorts the original list, and returns it
```Python
nums = [2,3,1]
x = sorted(nums)
print(nums)
print(x)
y = sorted(nums, reverse=True)
print(nums)
print(y)
```
```Terminal
[2, 3, 1]
[1, 2, 3]
[2, 3, 1]
[3, 2, 1]
```
### Membership and searching
#### in
- The `in` operator can check for an object inside on an array
```Python
coolPeople = ["neud", "rach", "miya", "bonk"]
print("neud" in coolPeople)
print("bins" in coolPeople)
```
```Terminal
True
False
```
#### index()
- The `index()` method returns the position at the first occurrence of the specified value
- If there are multiple items of the same value, only the index where the item first appeared is returned
- A second argument can be added to start searching from a particular index onwards
- If the item does not exist, it will raise an error
```Python
fruits = ['apple', 'banana', 'cherry', 'durian', 'banana']
print(fruits.index("cherry"))
print(fruits.index("banana"))
print(fruits.index("banana", 2))
```
```Terminal
2
1
4
```
#### count()
- The `count()` method can count the occurrence of a particular item in a list
```Python
nums = [1,2,3,3,3]
print(nums.count(3))
```
```Terminal
3
```
### Copying
- You cannot simply copy a list by typing `list2 = list1`, because `list2` will only be a reference to `list1`, and changes made in `list1` will also appear in `list2`
```Python
list1 = [1,2,3]
list2 = list1
list1.remove(1)
print(list1)
print(list2)
```
```Terminal
[2, 3]
[2, 3]
```
#### Slicing
- Using [slicing](#Reading), we can copy a list
```Python
list1 = [1,2,3]
list2 = list1[:]
list1.remove(1)
print(list1)
print(list2)
```
```Terminal
[2, 3]
[1, 2, 3]
```
#### list()
- Using the `list()` constructor, we can also copy a list
```Python
list1 = [1,2,3]
list2 = list(list1)
list1.remove(1)
print(list1)
print(list2)
```
```Terminal
[2, 3]
[1, 2, 3]
```
#### copy()
- The `copy()` method copies a list
```Python
list1 = [1,2,3, [4, 5, 6]]
list2 = list1.copy()
list1.remove(1)
print(list1)
print(list2)
```
```Terminal
[2, 3, [4, 5, 6]]
[1, 2, 3, [4, 5, 6]]
```
- However, this is only a shallow copy, meaning that nested lists that are modified will appear in the same in both
```python
list1 = [1,2,3, [4, 5, 6]]
list2 = list1.copy()
list1[4][2] = 10
print(list1)
print(list2)
```
```Terminal
[1, 2, 3, [4, 5, 10]]
[1, 2, 3, [4, 5, 10]]
```
#### deepcopy()
- `deepcoopy()` can do what `copy()` can't
- It needs to be imported though
```Python
from copy import deepcopy

list1 = [1,2,3, [4, 5, 6]]
list2 = deepcopy(list1)
list1[3][2] = 10
print(list1)
print(list2)
```
```Terminal
[1, 2, 3, [4, 5, 10]]
[1, 2, 3, [4, 5, 6]]
```
### List comprehension
- List comprehension help help us make lists of things in just one line! wow!
```Python
newlist = [x for x in range(10)]
print(newlist)
```
```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
- The format is as such:
```Python
newlist = [expression for item in interateble if condition == True]
```
- The expression can be modified to change the output
```Python
newlist = [x*2 for x in range(10)]
print(newlist)
```
```Terminal
[0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```
- We also can have an optional condition to filter the results
```python
newlist = [x for x in range(10) if x%2 == 0]
print(newlist)
```
```
[0, 2, 4, 6, 8]
```
- The expression can also have an `if` condition to manipulate the outcome
```Python
newlist = ["odd" if x % 2 == 1 else "even" for x in range(10)]
print(newlist)
```
```Terminal
['even', 'odd', 'even', 'odd', 'even', 'odd', 'even', 'odd', 'even', 'odd']
```
## Tuple
- Tuples are like lists, but they are immutable, meaning they cannot be modified like strings
- A tuple can be defined using a `tupe()` constructor, or with parentheses `()`
```Python
x = (1,2,3)
y = tuple()
z = ()
```
- A tuple with a single item has to include a comma or it will not be recognised as a tuple
```python
nums = (1)
print(type(nums))
nums = (1,)
print(type(nums))
```
```Terminal
<class 'int'>
<class 'tuple'>
```
- We can only read from a tuple, we cannot add to it, modify items, or delete items
```python
x = (1,2,3)
print(x[0])
del x[0]
x[0] = 10
```
```Terminal
1
TypeError: 'tuple' object doesn't support item deletion
TypeError: 'tuple' object does not support item assignment
```
### Operations
- `len()` prints the length of a tuple
```Python
x = (1,2,3)
print(len(x))
```
```Terminal
3
```
- `+` joins tuples
```Python
x = (1,2,3)
y = (4,5,6)
z = x + y
print(z)
```
```Terminal
(1, 2, 3, 4, 5, 6)
```
- `* `multiplies tuples
```Python
x = ("dan heng",)
y = x * 3
print(y)
```
```Terminal
('dan heng', 'dan heng', 'dan heng')
```
- `in` can check if an item is in a tuple
```Python
x = ("neud" , 17, "yellow")
print("neud" in x)
```
```Terminal
True
```
- We can also use a `for` loop
```Python
x = (1,2,3)
for i in x:
	print(i)
```
```
1
2
3
```

### Unpacking tuples
- Unpacking a tuple allows us to give multiple variables values at the same time
```Python
nums = (1,2,3)
x,y,z = num
print(x)
print(y)
print(z)
```
```Terminal
1
2
3
```
## Set
- A set is an unordered collection of unique values
- Sets do not allow duplicate values
- Sets are mutable, but the values inside are immutable
- Sets can be defined using the `set()` constructor or with angle brackets `{}` 
- Empty sets cannot be created with `{}`, the `set()` constructor must be used
### Operations
- `|` creates a union between two set (i.e. joins two sets together)
```Python
x = {1,2}
y = {3,4}
z = x | y
print(z)
```
```Terminal
{1, 2, 3, 4}
```
- `&` creates an intersection between the two sets (i.e. what is common in both sets)
```python
x = {1,2,3,4}
y = {1,2,3,4,5,6,7,8,9,10}
z = x & y
print(z)
```
```Terminal
{1, 2, 3, 4}
```
- `-` find the difference in two sets(i.e items in the set on the left but not the right)
```Python
x = {1,2,3,4}
y = {1,2,3,4,5,6,7,8,9,10}
z = y - x
print(z)
```
```
{5, 6, 7, 8, 9, 10}
```
- `^` find the symmetric difference in two sets (i.e. items that are in both sets, but not in their intersection)
```Python
x = {1,2,3,4,69,420}
y = {1,2,3,4,5,6,7,8,9,10}
z = y ^ x
print(z)
```
```Temrinal
{420, 69, 5, 7, 6, 8, 9, 10}
```
![[set operations.png]]
### Comparisons
- We can also check if an element is a subset or a superset
- A proper subset/ superset is a set in which all elements inside it are in another, but it is not equal to the other subset
![[set comparisons.png]]
 - We can also use the `in` operator on a set
```Python
print(0 in {0,1,2})
```
```Terminal
True
```
## Dictionary
- Dictionaries store items in key value pairs
- A key is separated from its value by a colon (`:`)
- Each pair is separated by a colon
- A dictionary can be defined by a the `dict()` constructor or `{}`
```Python
{}
dict()
{"name": "neud", "age": 17}
```
- Dictionaries are unordered, mutable and do not allow duplicate keys
- They do allow duplicate values
- Keys must strings, numbers or tuples and not any other type
### Access
- Dictionary items can be accessed by a key
```Python
profile = {"name": "neud", "age": 17}
print(profile["name"])
```
```Terminal
neud
```
- Trying to access a key that is not in the dictionary will result in an error
- `get()` does the same thing, but returns `None` if the item does not exist
```Python
profile = {"name": "neud", "age": 17}
print(profile.get("name"))
print(profile.get("cock"))
```
```
neud
None
```
- We can use the `keys()` method to list all of the keys in a dictionary
- `values()` will list all of the items in a dictionary
- `items()` will return each key value pair as a tuple, in a list
```Python
profile = {"name": "neud", "age": 17}
print(profile.keys())
print(profile.values())
print(profile.items())```
```
['name', 'age']
['neud', 17]
[('name', 'neud'), ('age', 17)]
```
- To determine if a key is in a dictionary, we can use an `in` keyword
```Python
profile = {"name": "neud", "age": 17}
print("name" in profile)
print("cock" in profile)
```
```Terminal
True
False
```
- We can also use a for loop to print all items in a dictionary
- Looping through a dictionary will loop through its keys
```python
profile = {"name": "neud", "age": 17}
for i in profile:
	print(i, profile[i])
```
```Terminal
name neud
age 17
```
- Looping through `items()` loops through every key-value pair
```Python
profile = {"name": "neud", "age": 17}
for i in profile:
	print(key, value)
```
```Terminal
name neud
age 17
```
### Add and update
- Add/ update dictionary items by calling its key
```Python
profile = {"name": "neud", "age": 17}
profile["age"] = 18
print(profile)
profile["favourite_colour"] = "green"
print(profile)
```
```Terminal
{'name': 'neud', 'age': 18}
{'name': 'neud', 'age': 18, 'favourite_colour': 'green'}
```
- You can also use the `update()` method
```python
profile = {"name": "neud", "age": 17}
profile.update({"age": 18})
print(profile)
profile.update({"favourite_colour": "green"})
print(profile)
```
```Terminal
{'name': 'neud', 'age': 18}
{'name': 'neud', 'age': 18, 'favourite_colour': 'green'}
```
- `update()` takes in multiple key-value pairs at once
```python
profile = {"name": "neud", "age": 17}
profile.update({"age": 18, "favourite_color": "green"})
print(profile)
```
```Terminal
{'name': 'neud', 'age': 18, 'favourite_colour': 'green'}
```
### Delete
- We can use `pop()` to delete a key-value pair
```python
profile = {"name": "neud", "age": 17}
profile.pop("age")
print(profile)
```
```Terminal
{'name': 'neud'}
```
- We can also use `del`
```python
profile = {"name": "neud", "age": 17}
del profile["age"]
print(profile)
```
```Terminal
{'name': 'neud'}
```
- Clear the dict by using `clear`
```python
profile = {"name": "neud", "age": 17}
profile.clear()
print(profile)
```
```Terminal
{}
```