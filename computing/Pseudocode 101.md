## Comments
- Comments can be written by adding `//` before the comment

## Variables
- Variables have to be declared first with their data type before they can be used
- They can then be assigned values of the according data type
- Variable names are case insensitive (i.e `Countdown` and `CountDown` refer to the same value)
- Variables names are alphanumerical, and can only start with a letter, not a digit

### Data types

|Keyword|Value|
|-|-|
|`INTEGER`| A whole number|
|`REAL`| A number capable of containing a fractional part|
|`STRING`| A string of zero or more characters|
|`BOOLEAN`| A `TRUE` /`FALSE` value|
|`CHAR`| A single character|
|`DATE`| A valid calender date|

```pseudo
DECLARE Counter: INTEGER // Declare variable
Counter <- 1             // Assigning value
```

> [!NOTE]
> If you are assigning a divided value to a variable, remember to make the variable have a real value, as division returns a real number, not an integer

## Constants
- Constants can be assigned values immediately with the `=` operator

```pseudo
CONSTANT HourlyRate = 6.50
```

## Arrays
- Generally, arrays has their first element started with an index of 1, unlike Python
- Arrays also use the same data type for each element
- Arrays can be stored into other variables, which are also arrays and have the same size and data type

```pseudo
SavedGame <- NoughtsAndCrosses
```

### 1-Dimensional
- Arrays are declared using the `:` operator 
- The `ARRAY` keyword next to the upper and lower bound
- The upper and lower bound must be in square brackets, with a colon separating them
- Declare the data type using the `OF` keyword

```pseudo
DECLARE StudentNames : ARRAY[1:30] OF STRING
```

- We can also assign values using its index
- Use the variable assignment operator `<-`

```pseudo
StudentNames[1] <- 'Ali'
```

- To assign multiple indexes to the same value, we should not do this

```pseudo
StudentNames[1 TO 30] <- " "
```

- This is because you cannot refer to a group of elements in an array
- Instead, use a for loop

```pseudo
FOR Index = 1 TO 30
	StudentsName[Index] <- " "
ENDFOR Index
```

### 2-Dimensional
- A 2-dimensional array islike a table
- The `ARRAY` keyword next to the upper and lower bounds
- The upper and lower bound must be in square brackets, with a colon separating them
- A comma is used to separate the upper and lower bounds of each dimension
- Declare the data type using the `OF` keyword

```pseudo
DECLARE NoughtsAndCrosses [1:3, 1:3] OF CHAR
```

Visually, this is the array generated

|ㅤ|ㅤ|ㅤ|
|-|-|-|
|ㅤ|ㅤ|ㅤ|
|ㅤ|ㅤ|ㅤ|

- We can also assign values using the index
- Use the variable assignment operator `<-`

```pseudo
NoughtsAndCrosses[2,3] <- 'X'
```

Visually, this is the new array

|ㅤ|ㅤ|ㅤ|
|-|-|-|
|ㅤ|ㅤ|X|
|ㅤ|ㅤ|ㅤ|

## Classes
_have not learned this yet lol_ 
## Input and output
- We can receive user input using the `INPUT` keyword

```pseudo
INPUT Answer
```

- We can output statements using the `OUTPUT` keyword
- Multiple values can be outputted at once

```pseudo
OUTPUT Score
OUTPUT "Your score is ", Score, "!"
```

## Math

|Sign|Meaning|
|-|-|
|`+`| Addition|
|`-` | Subtraction|
|`*`|Multiplication|
|`/`| Division|

- Division always returns a `REAL` value
- Modulus and floor division can be used, with keywords `MOD` and `DIV` respectively, but their use needs to be explained explicitly and not assumed

## Logic

|Sign| Meaning|
|-|-|
|`>`| Greater than|
|`<`| Less than|
|`>=` |Greater than or equal to|
|`<=` |Less than or equal to|
|`=` |Equal to|
|`<>` |Not equal to|

- They are the same signs in Python, expect for `=` and `<>` 
- There are are also `AND`, `OR`, and `NOT` keywords

### if statements
- If statements need an `IF` condition, and a `THEN` block to state the actions to be done, and finally an `ENDIF` to show that the if block has ended
- They may also have an `ELSE` block, but there is no `ELIF` in python, you need to nest the if inside

```pseudo
If Bitches < 1:
	THEN
		OUTPUT "You have no bitches!"
	ELSE
		IF Bitches == 1:
			THEN
				OUTPUT "You have ", Bitches, " bitch!"
			ELSE
				OUTPUT "You have ", Bitches, " bitches!"
		ENDIF
ENDIF
```

## Loops
### for loops
- for loops are written like a `for i in range(1,10)` in Python.
- They are written in the form `FOR i = 1 TO 10`
- There must be a lower limit and an upper limit, and both need to be an integer
- The variable is assigned for each of the values from the lower limit to the upper limit inclusive
- If the lower limit is equal to the upper limit, it will only run once
- If the lower limit is higher than the upper limit, it will not run at all.
- An `ENDFOR` is needed at the end

```pseudo
FOR Row = 1 TO 10
	RowTotal = 0
	FOR Column = 1 TO 10
		RowTotal <- RowTotal + Amount[Row, Column]
	ENDFOR COlumn
	OUTPUT "Total for Row ", Row, " is ", RowTotal
	Total <- Total + RowTotal
ENDFOR Row
OUTPUT "The grand total is ", Total
```

- For loops can also have a optional `STEP` parameter, each time the loop repeats, `i` increases by the `STEP`
- If `i` is greater than or equal to the upper limit, the loop will terminate.
- `STEP` can be negative

```pseudo
FOR i = 2 TO 10 STEP 2
	OUTPUT i
ENDFOR i
```

```output
2
4
6
8
10
```

### while loops
- A while loop is repeated while a condition is still true

```pseudo
WHILE number < 10 DO
	number <- number + 1
ENDWHILE
```

### repeat until loops
- A repeat until loops is repeated until a condition is true

```pseudo
REPEAT
	number <- number + 1
UNTILL number = 10
```

## Functions
- A function is a block of code that is reused
- It has to have a return value
- They also need to state what data type it returns, and it can only return values of that data type
```pseudo
FUNCTION count RETURNS INTEGER
	FOR i = 1 TO 10
		number <- i
	ENDFOR i
	RETURN number
ENDFUNCTION
```

- A function can also have parameters
- The data type of the integer must be specified

```pseudo
FUNCTION Max (Number1: INTEGER, Number2: INTEGER) RETURNS INTEGER
	IF Number1 > Number2
		THEN
			RETURN Number1
		ELSE
			Return Number2
	ENDIF
ENDFUNCTION
```

- Functions should be called when their return value is stored in a variable, or outputted, never on its own

```
Max = Max(1,10)
OUTPUT "The maximum is ", Max(1,10)
```

## Procedures
- A procedure is like a function, except that it does not return anything
```pseudo
PROCEDURE count 
	FOR i = 1 TO 10
		OUTPUT i
	ENDFOR i
ENDPROCEDURE
```
- They can also take in parameters
```pseudo
PROCEDURE count  (Number1: INTEGER, Number2: INTEGER)
	FOR i = Number1 TO Number2
		OUTPUT i
	ENDFOR i
ENDPROCEDURE
```

## File I/O
- Files can be opened using the `OPENFILE` keyword
- It has different modes

|Keyword| Mode|
|-|-|
|`READ`| Reads data from the file|
|`WRITE` | Creates a new file, or if the file already exists, clears it, then writes onto it|
|`APPEND`| Adds data to the end of the file|

```pseudo
OPENFILE Test.txt FOR READ
```

- Data can be read using the `READFILE` command after it has been opened in `READ` mode
- It only reads the next line
- The line that is being read has to stored in a variable with a data type `STRING`
```pseudo
OPENFILE Test.txt FOR READ
READFILE Test.txt, Line
```
- The function `EOF` is used to test wether the file pointer is at the end of the file
```pseudo
OPENFILE Test.txt FOR READ
REPEAT 
	READFILE Test.txt, Line
	OUTPUT Line
UNTILL EOF(Test.txt)
```

- We can write data into a file using the `WRITEFILE` keyword after it has been opened in `WRITE` or `APPEND` mode
```pseudo
OPENFILE Test.txt for WRITE
WRITEFILE Text.txt, ":3"
```

- Files need to be closed after they have been opened using the `CLOSEFILE` keyword
```pseudo
CLOSEFILE Test.txt
```

## Random number
- `RANDNDOMBETWEEN(0,10)` generates a random integer between min and max
- `RND()` generates a random real number between 0 and 1