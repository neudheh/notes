## List
- Lists are used to store multiple items in a single variable
- Lists are ordered, mutuable and allow duplicate values
- Mutable means that a list tiems can be added, updated and removed
### Creating
- Create a list using square brackets `[]` or the `list()` constructor
- List items can be of any data type, and can have different data types
- Lists can also contain sublists, which is known as a nested list
```Python
nums  = []
nums = list()
nums = [1,2,3,4,5]
nums = list(range(10))
characters = list(spiderman)
fruits = ["apple", "banana", "orange"]
list1 = ["abc", 34, True, 40, "male"]
list2 = [[1,"apple"],[2,"orange"],[3,"pear"]]
```
### Read
- Lists items are indexed and we can refer to them by the index number
- Lists items also can be sliced, like strings ![[Data types#Indexing and slicing]]
```python
fruits = ["apple", "banana", "cherry","durian"]
print(fruits[0])
print(fruits[1])
print(fruits[-1])
print(fruits[-2])

print(fruits[1:3])
print(fruits[:3])
print(fruits[1:])
print(fruits[1:-1])
```
```terminal
apple
banana
durian
cherry
['banana', 'cherry']
['apple', 'banana']
['banana', 'cherry', 'durian']
['banana', 'cherry']
```
- We can also use a for loop to loop through each item in the list
```python
fruits = ["apple", "banana", "cherry", "durian"]
for i in fruits:
	print(i)
```
```terminal
apple
banana
cherry
durian
```
- The `index()` method returns the position at the first occurence of the specified value
- If there are multiple items of the same value, only the first index value of that item is returned
- A second aregument can be added to start searching from a particular index onwards
- If the item does not exist, it will raise an error
```Python
fruits = ['apple', 'banana', 'cherry', 'durian', 'banana']
print(fruits.index("cherry"))
print(fruits.index("banana"))
print(fruits.index("banana",2))
```
```Terminal
2
1
4
```
### Adding list items
#### Append
- The `append()` method is used to append an element to the end of a list
```python
num = [1,2,3,4,5]
num.append(6)
print(num)
num,append([7,8,9])
print(num)
```
```
[1, 2, 3, 4, 5, 6]
[1, 2, 3, 4, 5, 6, [7, 8, 9]]
```
#### Insert
- The `insert()` method inerts a value at the specified index
```python
fruits = ["apple", "banana", "orange"]
fruits.insert(2,"cherry")
print(fruits)
```
```
["apple", "banana", "cherry", "orange"]
```
#### Extend
- A list can be extended using elements from another list using the `extend()` method
- It will modify the first list
- The resultant will contain the elements in both lists (i.e the resultant list is not a nested list)
```Python
num = [1,2,3,4,5]
num.extend([6,7,8])
print(num)
```
```Terminal
[1, 2, 3, 4, 5, 6, 7, 8]
```
#### Using operator
- Two lists can be joined together using the `+` operator
```Python
num = [1,2,3,4,5]
num = num + [6,7,8]
print(num)
```
```Terminal
[1, 2, 3, 4, 5, 6, 7, 8]
```
- We can also repeat a list multiple times with the `*` operator
```python
num = [1]
print(num * 3)
```
```
[1, 1, 1]
```
### Update
- To update a value in the list, we can use its index value
```python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits[1] ='blackcurrant'
print(fruits)
```
```terminal
['apple', 'blackcurrant', 'cherry', 'durian']
```
- We can update more than one item by specifying a range of index numbers where you want to insert the new items
```python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits[1:3] = ['blackcurrant', 'watermelon']
print(fruits)
```
```terminal
{'a': 'apple', 'b': 'berries', 'c': 'carrot', 'd': 'doughnut'}
```
- If you insert more items than you replace/ update, the new items will be inseerted where you specified, and remaining items will move accordingly
```python
fruits = ['apple', 'banana', 'cherry', 'durian']
fruits[1:3] = ['blackcurrant', 'watermelon','strawberry']
print(fruits)
```
```
['apple', 'blackcurrant', 'watermelon', 'strawberry' 'durian']
```
### Delete
### Remove by value
- The `remove()` method will remove an item based on its value
- If there are multple items of the same value, it will only return the first item
- It will raise an error if the value is not in the list
```python
num = [10,20,30]
num.remove(20)
print(num)
```
```
[10,30]
```
### Remove by index
- The `pop()` method removes the elemnt at the specified position
- If no psotion is specified, the last item is removed by default
- `pop()` returns the removed value
```python
num = [1,2,3,4,5]
num.pop()
print(num)

x = num.pop(1)
print(num)
print(x)
```
```Terminal
[1,2,3,4]
[1,2,4]
```
### Del keyword
- The `del` keyword is used to delete objects (variable, lists, part of a list, everything)
```python
num = [1, 2, 3, 4, 5]
del num[2]
print(num)
del num
print(num) # error, becuase del deleted the whole num list entirely
```
```
[1, 2, 4, 5]
NameError: name 'num' is not defined
```
### Clearing a list
- To clear all element sin a list, use the `clear()` method
```python
num = [1,2,3]
num.clear()
print(num)
```
```Terminal
[]
```
### Methods
#### Min, Max, Sum
- If the list consists of all integer elements, `min()`, `max()` and `sum()` gives the minimum item, maximum item and total sum value of the list
```python
num = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(min(num))
print(max(num))
print(sum(num))
```
```Terminal
0
9
45
```
- For a list of strings, `min()` and `max()` will return the string with the lowest and highest ASCII value respectively
	- Lowercase characters have a higher ASCII value than their uppercase counterparts
	- Alphabetical order
```python
array = ['a', 'b', 'c', 'Z', 'z']
print(min(array))
print(max(array))
```
```terminal
Z
z
```
#### Reversing
- The entire elements in the list can be reversed by using the `reverse()` method
- `reverse()` edits the original list and reverses it, and does not return anything
```python
nums = [1, 2, 3]
x = nums.reverse()
print(nums)
print(x)
```
```
[3, 2, 1]
None
```
- `reversed()` reverses the original list and returns the reveresed array
```Python
nums = [1, 2, 3]
x = reversed(nums)
print(nums)
print(list(x))
```
```Terminal
[1, 2, 3]
[3, 2, 1]
```
#### Sorting
- `sort()` edits the original list and sorts it, and does not return anything
```Python
nums = [2, 3, 1]
x = nums.sort()
print(nums)
print(x)
```
```Terminal
[1, 2, 3]
None
```
- `sorted()` sorts the original list and returns it
```Python
nums = [2, 3, 1]
x = sorted(nums)
print(nums)
print(x)
```
```Terminal
[2, 3, 1]
[1, 2, 3]
```
#### Membership and searching
- We can use the `in` operator to see if a specified value is in a list
```Python
coolPeople = ["neud", "rach", "miya", "bonk"]
print("neud" in coolPeople)
print("bins" in coolPeople)
```
```Terminal
True
False
```
- The `count()` method can count the occurence of a particular item in a list
```Python
nums = [1, 2, 3, 3, 3]
print(nums.count(3))
```
```Terminal
3
```
### Copying list
- You cannot copy a list by typing `list2 = list1`, becuase list
#### Slicing
- 
#### list()
- 
#### Copy()
- 
#### Deepcopy()
- 
### List comprehension
- 
## Tuple
- 
### Unpacking tuples
- 
## Set
- 
### Operations
- 
### Comparisons
- 
## Dictionary
- 
### Create
- 
### Acess
- 
### Update
- 
### Add
- 
### Delete
- 