#computing
# Program Language
- A collection of instructions for a computer is known as a program
- Usually written using a human-readable programming language such as Python
- The human readable form of a program is called source code or code for short
- Programming languages have strict rules for how instructions can be written such that source code is readable to computers
- Running or executing a program is to make a computer follow the instructions of the program
# Literals
- Python, like most programming languages, deals with values (a.k.a literals)
- Different types of literals, which are also known as [[Data types]]
# Variables
- One way to manipulate literals is to give names to them, and the named values are called variables
- Variables are a named storage space for a value that can be changed while the program is running
- We can assign values to variables and read values from variables
- Variables need to be assigned a value first to be read
- Can be assigned a value as shown```
```python
year = 2021
```
- A variables is initialised when a value is assigned to it
- A variable only keeps the last value that was assigned to it, and previous values, if any, are discarded
- What comes after the equal sign does not have to be a literal, and can have calculations and other variables
- Python will fully evaluate what comes after the equal sign before assigning the result to the variable name
- It is possible to read the value of a variable, manipulate it, and then re-assign it to the same variable
## Rules to naming a variable
- Can contain upper and lowercase letters from A-Z, and the underscore (\_)
- Can contain numbers from 0-9, but not as the first character
- Cannot contain spaces or any special symbols
- Cannot contain any reserved words (or keywords) that have special meanings in python
	(if, elif, else, and, or, not, None, True, False, def, pass, return, for, in, while, break, continue, is, from, import, as, global, nonlocal, with, try, assert, raise, except, finally, class, del, yield, lambda)
- As a convention, identifies in python are written in lowercase with words separated by underscores (e.g. total_score)
# Comments
- Comments allow programmers to insert explanations for human readers of the code that are ignored by the computer
- In Python, comments start with the hash symbol (#) and finish when the line ends
- Can be written at the start, at the same line as the code or at the end
	- Comments at the start of the program explain the purpose of the program and its expected inputs and outputs
	- In-line comments usually serve to explain the purpose of the particular lines of code