## Program Language
- A collection of instructions is called a program
- The human readable for for a program is called the source code/ code
- To run or execute a program is to make a computer follow the instructions in the program
## Indentation
- Indentation is the number of spaces at the beginning of the code line
- Normally 4 spaces or a tab character is used
- Indentation is used to indicate a block of code
- The following code with result in an error

```Python
if 5 > 2:
print("Five is greater than two!")
```

```Terminal
IndentationError: expected an indented block
```

- The number of spaces must be the same in the same block of code

```Python
if 5 > 2:
	print("Five is greater than two!")
		print("Wow!")
```

```Terminal
IndentationError: Unexpected indent
```

## Naming conventions
- Use meaningful identifier names
- Modules should have short, all-lowercase names and separated by underscores if it helps
- Classes should used the CapWords convention (e.g. `MyCoolClass`)
- Functions, Variable and Method names should be lowercase, and separated by underscores if it helps
- Constants are defined in the beginning of the program and in all caps, with underscores separating words
- Private identifiers should have an underscore as their first character
- Don't use double underscores as Python uses this notation
## Comments
- Comments can be written to explain code, improve readability by providing insight or summarisation
- Comments are also used as a part of documentation to help you or others understand the code, especially after a long period of time
- Comments start with a `#` and the rest of the line is regarded as a comment

```python
# wow! i'm a comment
print("Very cool!") #i'm an inline comment!
```

- Comments at the start of a program explain what it does, and expected inputs and outputs
- Inline comments explain the purpose of particular lines of code
## Modules
- A module is a collection of variables and functions that need to be loaded before used
- It can be useful to keep things organised
- We don't usually need all the functions and variable provided by the system to be available all the time
- But loading functions and making them available takes time and computer memory
- It becomes harder to choose names for variables and functions as the names chosen might overwrite or clash with the ones provided by Python
### Importing a module
- Import a module using `import <module>`
- We can rename them using `import <module> as <name>`
### Importing functions and variables
- We can import functions/ variables from a module by using `from <module> import <function>`
- We can import all the functions/ variables by using `from <module> import *`