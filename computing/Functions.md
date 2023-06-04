## Decomposing a problem
- Decomposition breaks down a problem into smaller parts called sub-problems
- Each sub-problem can be examined and solved independently of the whole, and then they can be combnined to solve the original probelm
### Incremental approach
- Identify quantitive features of the input or output that cuase the problem to be too large to handle
- The solution to a small version of the problem (where one or more of these features reduced) can be found and gradually extended to larger versions of the problem
## Modular appoarch
- Identify tasks that are of different nature and seperate them from each other to become distinct (and sometimes unrelated) sub-problems
- Sub-problems are different from each other
## Generalization
- Solutions that solve two different problems but are similar to each other can be generalised to produce a single solution that can solve multiple problems
## Subroutines
- Subroutiness allow us to manage and structure our probgrams by breaking them up into smaller chunks of code
- This is known as modular design
- Modular design allows us to debug easily, especially when dealing with a large program
- There are two types of subroutines
	1. Functions - subroutines that allows us to have both input and output. The fuction accepts input and process them into output. They must return at least one value, a.k.a. "return value"
	2. Procedures - subroutines that do not return values
### Advantages
1. Organization
	- Subroutines help break programs into smaller and modular chunks, almost like a mini-program that we can write seprately from the main program, without having to think of the rest of the program while we write it
	- This allows us to reduce a complicated program into smaller, more manageable chunks, reducing overall complexity of the program
2. Abstractions
	- We can use a subroutine at anytime, using its unique name and appropriate inputs
3. Reusability 
	- It supports code resuability and reduces repetitive code
	- Subroutines can also be shared with other programs, reducing the need to code from scratch
4. Modifying
	- When we need to extend our program to handle a case it never handeled before, subroutines allow us to make changes in one place and have that change take effect everytime that subroutine is called
5. Testing
	- The program is easier to test and debug since each subroutine is self-contained
	- Once a subroutine is working properly, there is no need tot test it again unless it has been modified
## Function syntax
### Defining a function
```Python
def addition(a,b):
	"""This function adds two numbers, a and b together and returns the sum"""
	return a + b
```
- The `def` keyword makrs the start of the function
- `addition` is the function name
	- Function names must be uniquely identifiable
- `a,b` are the values in the brackets, and are known as parameters
	- Parameters are optional, and are taken in befor running the code block
- It may return a value as a result using a return statement (`return a + b` )
- If there is no return statement, the function returns none
- The docstring (`"""This function adds two numbers, a and b together and returns the sum"""`) is used to describe what the function does and can be multiple lines long
- All statements msut be indented by 4
### Function call
```python
result = addition(1,2)
```
- `addition(1,2)` is known as the function call
- `1,2` are known as arguments
- Arguments are stored as variable in the function. In this case, 1 is stored in `a` while 2 is stored in `b`
- `a` and `b` can be used by the function in its statements
- If the function does return a value, it will be stored in `result`, else `result = None`
## Function that does nothing
```python
def utterly_useless():
	pass
```
- `pass` indicates that there is nothing to be done in the funciton boydt
- It is used when we want to define a function to do something, but we are not ready to code it yet
### Function with default arguements
```python
def addition(a,b=1)
	return a + b
print(addition(9))
```
```terminal
10
```
- If the value of b is not specified in the function call, e.g. `addition(9)`, `b` will get its default value.
*\* args and \*\*kwargs is not in syllabus.*
## Global and local variables
- Global variables are variable defined outside a function body
- Local variables are defined inside a function body
- Local variables can only be accessed only inside the funciton they are declare, while global variable can be acessed trhoughout the program
	- The following code will result in an error
```python
def Hello():
	msg = "Hello World"
	print(msg)

Hello()
print(msg)
```
- If the a local varibale has the same name as a global variable, the function will use the value inside the function only
```python
msg = "Hello world"

def Hello():
	print("From Hello(): ",msg ) # becuase there is no local variable, it uses the global msg

def HelloToo():
	msg = "Hello Singapore"
	print("From HelloToo(): ", msg) #uses the local msg

print("Global: ", msg)
Hello()
print("Global: ", msg)
HelloToo()
print("Global: ", msg)
```
```Terminal
Global: Hello World
From Hello(): Hello World
Global: Hello World
From HelloToo(): Hello Singapore
Global: Hello World
```
``
- To change/ edit/ assiign the value ot the gobal variable, we can use `global`
```python
msg = "Hello world"
def HelloTree():
	global msg
	msg = "Hello Mom"
	print("From HelloTree(): ", msg)

print("Global: ", msg)
HelloTree()
print("Global: ", msg)
```
```Terminal
Global: Hello World
From HelloTree(): Hello mom
Global: Hello mom
```