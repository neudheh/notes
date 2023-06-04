## Algorithm
- An algoritm is a step-by-step procedure (well-defined instructions) to solve a given problem
- We can represent algorithms as [[Flowchart 101|flowcharts]] and [[Pseudocode 101|pseudocode]]
## Constructs
### Sequence construct
- A sequence construct involves perfoming multiple instructions in a fixed order
- The flowchart looks like this
![[Sequence construct.png]]
- Every step must be carried out in the specific order or the algorithm may not work correctly
### Selection construct
- A selection construct involves choosing between two or more branches based on a particular condition
- The flowchart looks like this![[Selection construct.png]]
- A selection is a decision or question that allows the inclusion of two or more paths in an algorithm
- Selection allows us to include more than one path in an algorithm
- Two branches follow from a selection
### Iteration (loop) construct
- Iteration constructs invovles repeating instructions while a particular condition is true
- The flowchart looks like this![[Iteration construct.png]]
- An iteration, a.k.a. a loop allows an algorithm to repeat certian steps untill told to stop or a particular condition is met
- Iteration allows an algorithm to be simplified by stating that certian steps will be repeated untill told otherwise
## If-elif-else
- A statement is a unit fo source code that represents a complete set of instructions
- An if-elif-else statement happens to be a compound statement that can contain multiple statements as it componenets
```Python
text = input("Enter text: ")
if text == "":
    print("Blank Input Not Allowed")
elif text == "P@55w0rd":
    print("Correct Password")
    print("Access Granted")
else:
    print("Wrong Password")
    print("Access Denied")
print("Goodbye")
```
- The `if` statement has the first condition. If the condition is met, it runs the statements (`if` block)
- The `elif` statemtns has the second condition. Elif is a abbreviation of else if. If the first condition is not met, then it checks if it meets the `elif` condition. If the `elif` condition is met, it runs the statements (`elif` block)
- If none of the conditions are met, it runs the `else` block.
## While loop
- A while loops runs the statements in the `while` block while the condition is true
```Python
name = ""
while name == "":
    name = input("Enter name: ")
print("Hello " + name)
```
- The statement must eventually become false or the program will go into an infinite loop
- This program will repeat while name is an empty string, and will repeatedly ask for input untill name is no longer empty
- When the statment becomes false, it runs the rest of the lines of code in the algorithm
## For loop
- A for loop will iterate over (go through) each item in a list, and run the statements in the `for` block for every item in a list
```Python
items = [1, 2, 4, 8, 16, 32]
for item in items:
    print(item)
```
- `item` references the current item the algorithm is on in the array
- We can also loops through the characters of a `str` and the keys of a `dict`
### Range
- When one argument is specified in the `range(a)` function, it creates of set of numbers from 0 to a - 1
- When to arguments are specified in the `range(a,b)` function, it creats a set of numbers from a to b-1
- A third value can be specified in the `range(a,b,c)` function, where c is the increment. By default, this is 1
```python
for x in range (2,11,2):
	print(x)
```
```Terminal
2
4
6
8
10
```
## Break
- Break allows us to exit the loop
```Python
for x in "spiderman":
	if x == "m":
		break
	print(x)
```
```Terminal
s
p
i
d
e
r
```
## Continue
- Continue allows us to stop the current iteration of the loop and continue with the next
```Python
count = 0 

while count < 5:
	count += 1
	if count == 3:
		continue
	print(count)
```
```Terminal
1
2
4
5
```
## Pass
- `pass` acts as a placeholder when we are not usre how or what to do when a contision is met