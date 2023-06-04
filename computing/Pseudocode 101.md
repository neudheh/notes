- Keywords are always in upprcase (`IF`, `REPEAT`,`DECLARE`)
## Comments
- Comments are decalred using the `//`
```
// Wow! Look at me! I'm a comment!
```
## Data types
- `INTEGER` : A whole number
- `REAL`: Any real number (i.e. a float in Python)
- `CHAR`: A single character, declared with a `' '`
- `STRING`:  A sequence of zero or more characters, declared with a `" "`
- `BOOLEAN`: A `TRUE`/ `FALSE` Value
- `DATE`: A valid character date, written in `DD/MM/YYYY` and explain the format
## Variables
### Declaring
- Variables can be declared like this:
```
DECLARE VeryCoolVariableNameIKnowThankYou: INTEGER  
```
- `VeryCoolVariableNameIKnowThankYou` is the name of the variable
- `INTEGER` is the data type of the variable
- Variables names can only be alphanumeric
- They can only start with a letter
- They should be case insensitive (i.e. `Countdown and CountDown` should be the same variable)
### Updating
- To update the values of a variable, we can use
```
VeryCoolVariableNameIKnowThankYou ← 10
VeryCoolVariableNameIKnowThankYou ← VeryCoolVariableNameIKnowThankYou + 1
VeryCoolVariableNameIKnowThankYou ← A * B
```
## Constants
- Constants can be declared like this:
```
CONSTANT GoodsAndServicesTax = 0.08
```
- Only literals can be assigned to constants 
- Constants have the same naming conventions as variables
- Constants are usually declared at the begenning of the pseudocode
## Arrays
- Unlike Python, arrays have a fixed length
- The first element in an array has an index of 1
### Declaring
- Arrays can be declared like this:
```
DECLARE StudentNames: Array[1:5] OF STRING
```
- `[1:5]` is declaring the bounds of the array, where the array has a total of 5 elements
- `STRING` is the type of the elements in the array
In python, this would be like
```
StudentNames = ["","","","",""]
```
### Assigning
- To assign a value to a position array:
```
StudentsNames[1] ← "Ali"
```
- `[1]` is the index in the array to assign the value to
- Use a for loop to assign multiple indexes to the same value
```
FOR Index = 1 TO 30
    StudentNames[Index] ← ""
ENDFOR Index
```
## Input & Output
- To accept input
```
INPUT TotalIncome
```
- Input should always to be a variable
- To ouput a value
```
OUTPUT Taxes
```
- To output multiple values
```
OUTPUT "You have to pay $", Taxes
```
## String operators
- String operators suchs as concetation, searching and splitting should be explained clearly
- When using a function to convert a number into a string for output, the use of the function should be explained
## Math
|Symbol|Meaning|
|-|-|
|`+`|Addition|
|`-`|Subtraction|
|`*`|Multiplication
|`/`|Division|
|`MOD`|Modulus division|
|`DIV`|Floor division|
- Division always results in a real value
- `MOD` and `DIV` can be used, but should be explained explicitly and not asssumed
- Follows order of operations
## Logic
### Relational operators
|Symbol|Meaning|
|-|-|
|`>`| Greater than|
|`<`|Lesser than|
|`>=` |Greater than or equal to|
|`<=` |Lesser than or equal to|
|`=`|Equal to|
|`<>`|Not equal to|
### Logic operators
|Symbol|Meaning|
|-|-|
|`AND`|Both statemnts are true
|`OR`|Both statements are false|
|`NOT`|The statement is false|
- Relational and logic operators always results in a boolean
- Use parantheses if the statements gets complex
### If statements
- To use an if statement:
```
IF Bitches = 0
	THEN
		OUTPUT "You have no bitches."
	ElSE
		IF Bitches = 1
			THEN
				OUTPUT "You have a bitch!"
			ELSE
				OUTPUT "You have ", Bitches, " bitches!"
		ENDIF
ENDIF
```
- Unlike python, there is no `elif` 
- If statements may not have an else clause
- `Bitches = 0` and `Bitches = 1` are conditions
- `OUTPUT "You have no bitches."`, `OUTPUT "You have a bitch!"` and `OUTPUT "You have ", Bitches, " bitches!"` are statements
- Nested `IF`s should be indented
### For loops
- A For loop can be written as 
```
DECLARE n: INTEGER
n ←  0
FOR i = 1 TO 10
	n ← n + i
ENDFOR i
OUTPUT n
```
- `FOR i = 1 TO 10` is equivalent to `for i in range(1,11)` in python
- `ENDFOR` should have the identifier (which is n)
### While loops
#### Repeat untill a condition is true
```
DECLARE n: INTEGER
n ←  0
REPEAT
	n ← n + 1
UNTILL n = 10
```
### Repeat while a condition is true
```
DECLARE n: INTEGER
n ←  10
WHILE n > 0 DO
	n ← n - 1
ENDWHILE
```
## Functions
```
PROCEDURE Square (number:integer)
	DECLARE result: INTEGER
	result ← number * number
	RETURN result
```
## Random numbers
|Fuction|Use|
|-|-|
|`RANDOMBETWEEN(min,max)`|Generates a random integer between min and max (inclusive)|
|`RND()`|Generates a random real number between 0 and 1 (Inclusive)|