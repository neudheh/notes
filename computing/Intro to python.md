## Program Language
- A collection of instrutions is called  a program
- The human-readable form for a program is called socurce code or code for short
- To run or execute a program is to make a computer followthe instructions in the program
## Running your python code
### IDLE
1. Launch IDLE
2. File → New file
3. Enter your code and save it by going to File → Save
4. Run code by going to Run → Run Module
### Jupyter notebook
1. Open powershell
2. Change the directory to d: by entering `d:`
3. Launch Juypter by enetering `jupyter notebook`
4. Crate a new notebook by going to New → Python 3
5. Name your file and enter your code
6. Save your code by going to File → Save
7. Run your code by pressing Run
## Syntax
### Indentation
- The number of spaces a the beginning of the code line
- We usually use 4 spaces, or a tab
- Indentation is used to indicate a block of code
- The following code will result in an error
```python
if 5 > 2:
print("Five is greater than two!")
```
```Terminal
IndentationError: expected an indented block
```
- The number of spaces must be the same in the same block of code
```python
if 5 > 2:
	print("Five is greater than two!")
		print("Wow!")
```
```Terminal
IndentationError: unxepected indent
```
### Naming conventions
- Use meanginful identifier names for a variable, function, class, module and any other object
- Modules should have short, all-lowercase names, and seperated by underscores if it helps
- Class names shoudl use CapWords convention (e.g. MyCoolClass)
- Function, Variable and method names should be lowercase, and seperated by underscores if it helps
- constants are defined in the beginning of the progeam and in all cpas, with underscores seperating words
- Private identifiees cshould have an underscore as the first letter
- Don't use double underscores as python uses this notation
### Comments
- Comments can be written to explain code, or improve readability by providing insight or summarisation
- Comments are also used as part of documentation to help you or others understand the code, especially after a long period of time
- Comments start with a `#` and the rest of the line is regarded as a comment
```python
# wow! im a comment
print("very cool") # im an inline comment!
```
- Comments at the start of a program explain what it does, and expected inputs and outputs
- Inline comments to explain the purpose of particular lines of code