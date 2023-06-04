## Literals
- Values are known as literals
- Literals can be of a string, integer, float, or boolean
- There is also a special `None` value used to keep track of the fact theat that there is a value that is missing or there is no suitable value to be assigned to a variable
## Variables
- Variables are named values
- We can assign a value to a variable like this
```python
year = 2021
```
- What comes after the equal sign can abe a literal, calulations and othger variables
- Python will evaluate what comes after the equals sign first before siging the variable the value
- A variable in initailsied when a valhue is first stored in it
- A variable only keeps the last value that was assigned to it and discards previous vlauess
### Naming conventions
- Only can contain alpahnumeic characters and underscores
- Cannot start with a number
- Cannot have spaces or special symboles
- Cannot have python keywords (e.g `if`, `None`,  `for`)
## Data types
|Data type|Python name|Description|Example|
|-|-|-|-|
|Integer|`int`|Whole numbers|1234|
|Floating point|`float`|Real numbers|12.34|
|String|`str`|Text|"ABC123"|
|Boolean|`bool`|True or False value|True|
## Type casting
- Typecasting is converting from one type to another
- Tod do this in Python, we can simply use the python name of the data type like a function (`int()`, `float()`,`str()`,`bool()`)
## Integer
- Integers (`int`) are positive and negative whole numbers, including zero
- Integers have two formats:
	- Write out the digits with a possible negative sign in front (1.234 or -1.234)
	- Use a prefix before the number to represent binary, hexadesimal and ocatl number systems
|Number system|Prefix|
|-|-|
|Binary|`0b` or `0B`|
|Octal|`0o` or `0O`|
|Hexadecimal|`0x` or `0X`|
- The functions `bin()` and `hex()` can be used to convert a decimal number to binary and hexadecimal respectively
## Floating point
- A floating-point number (`float`) is a real number
- They have two formats
	- Digits of the float with the decimal point included explicitly (e.g. 123.4)
		- If there is no decimal point, python will treat it as an `int`
	- The form AeB or AEB to represent $A \times 10^B$ (e.g. 1234e2)
- Floats are not accurate due to the way they are stored
- Floats have to be between $1.79 \times 10^{308}$ and $-1.79 \times 10^{308}$ , or it will be converted to the special value of infinity, represented by `inf` or `-inf`
## Arithmetic operators
|Operator|Name|Example|
|-|-|-|
|`+`|Addition|`2+3=5`|
|`-`|Subtraction|`7-3=4`|
|`*`|Multiplication|`2*3=6`|
|`/`|Division|`20/8=2.5`|
|`//`|Floor division|`20/8=2`|
|`%`|Modulus|`20%8=4`|
|`**`|Exponentiation|`4**2=16`|
- Division will always result in a `float`
- All of these operators can be used on `int`s and `float`s
- Adding an `=` at the back of the operator allows us to update the value of a variable (e.g. `x += 1` is equal to `x = x + 1`)
## Strings
- Strings (`str`) are a series of characters, whcih can be a word, a sentence or a paragraph
- We can create strings in 4 ways
	1. ASCII
		- We can create a string by entering the ASCII code of the character into the function `ord()`
		- We can also get the ASCII value of the caracter by using `chr()`
		- To convert an uppercase letter to a lowercase letter, we add 32 to its ASCII Value
		 ```python
	   print(ord(78))
	   ```
		```Terminal
		N
		```
	2. Unicode
		- Enter `\u` followed by the unicode number for the character
		```python
		print(\u7434)
	   ```
		```Terminal
		琴
		```
	3. Double or single quotes
		- We can decare strings by surrounding the text with double (`" "`) or single (`' '`) quotes
	4. Multi-line string
		- Multiline strings are declared by surrounding text with three double (`" "`) or single (`' '`) quotes
		- They are usually used to create docstrings
### Escape characters
- We need escape characters to include characters in a string, which would otherwise result in a syntax error
- It can also continue a long line of code by putting a backslash (`\`) at the end of the line

|Escape character|Meaning|
|-|-|
|`\\`|Backslash( \\ )|
|`\'`|Single-quote( ' )|
|`\"`|Double-quote ( " )|
|`\n`|New line|
|`\t`|Tab|

### Indexing and slicing
- Each character in a string can be acessed by an index
- The first character of the string will be zero
- The last character of the sring can also have an index of -1, second last -2, etc..
- Strings are immutable, meaning we cannot replace a character in the sring by using `x[0] = "R"`
```python
string = "Hello World!"
print(string[0])
print(string[1])
print(string[2])
print(string[-1])
```
```Terminal
H
e
l
!
```
- We can acess multiple characters by slicing
- `x[a:b]` returns all characters in x from index a to b-1
- We can specify a thrid value c in `x[a:b:c]` to show the steps
	- C can be negative to go backwards
- Not specifying b indexes to the end of the string
- Not specifying a indexes from the beginning of the string
- For indexing or slicing, if one of the parameters are out of range, there will be an error
- For slicing, if a appears later in the string (assuming that c is positive), there will be an error
- If c is negative, there will be no error
```Python
string = "Hello World!"
print(string[0:2])
print(string[:4])
print(string[2:])
print(string[0:6:2])
print(string[::-1])
```
```Terminal
He
Hell
llo World!
Hlo 
!dlroW olleH
```
### len()
- The `len()` method returns the numer of characters in a string
```python
print(len("hello"))
```
```Terminal
5
```
### Operators
- `+` can be used to join string together
```Python
print("spider" + "man")
```
```Terminal
spiderman
```
- `*` can be used to repeat strings
```Python
print("ur mom " * 3)
```
```Terminal
ur mom ur mom ur mom
```
- `in` can be used to see if a string is in another string
```Python
print("ur" in "ur mom")
```
```Terminal
True
```
### Methods
- All these methods can be used by using `x.method("argument")`

|Method|Description|
|-|-|
|`count()`|Counts how many times a the argument occurs in the string|
|`find()`|Returns the index of the argument when it is found in the string, else it returns -1|
|`index()`|Same as `find()`, but it raises an error if not found|
|`lower()`|Converts all letters to lowercase|
|`upper()`|Converts all letters to uppercase|
|`title()`|Converts the first character of each word to uppercase|
|`strip()`|Removes whitespace from the beginning and end of a string. A value can be specified to strip the amount of character from the beggning and the end|
|`lstrip()`|Same as `strip()` but it only strips the leading whitespace|
|`rstrip()`|Same as `strip()` but it only strips the trailing whitespace|
|`isalphanum()`|Returns true if a string is alphanumeric and has at least 1 character, else it returns false|
|`isalpha()`|Returns true if a string is alphabetic and has at least 1 character, and false otherwise|
|`isnumeric()`|Returns true if a string is numeric and has at least 1 character, and false otherwise|
|`isupper()`|Returns true if a string is uppercase and has at least 1 character, and false otherwise|
|`islower()`|Returns true if a string is lowercase and has at least 1 character, and false otherwise|
|`isspace()`|Returns true if a string only contains whitespace characters and false otherwise|
|`startswith()`|Returns true if the string starts with the string specified|
|`endswith()`|Returns true if the string ends with the string specified|

### Formatting
- The `.format` method can be sued to insert values into strings
```Python
name = "Kevin"
print("Hi {}, welcome to my epic swag code".format(name))
```
```Terminal
Hi Kevin, welcome to my epic swag code
```
- It takes an unlimited amount of arguments, and ar e placed into the respective place holders
- Index numebers can be used to ensure arguments are palced into the correct placeholders, and the same index number can be used more than once
```Python
name = "Kevin"
age = 17
print("Welcome {0}! {0}'s age is {1}!".format(name,age))
```
```Terminal
Welcome Kevin! Kevin's age is 17!
```
- Inside the placeholders we can add a formatting type to format the result

|Formatting type|Result|
|-|-|
|`:0>6`|Formats the number to a fixed number of digits with zeros appended to the front|
|`:.3f`|To 3 decimal places|
|`:.3`|To 3 significant figures|
|`:10.3`|Makes the number 3 significant figures and10 characters long, and aligns it to the right|
|`:<10.3`|Makes the number 3 significant figures and 10 characters long, and aligns it to the left|
|`:^10.3`|Makes the number 3 significant figures and 10 characters long, and aligns it to the centre|
## Booleans
- A boolean (`bool`) are a `True` or `False` value
### Boolean operators
|Operator|Function|
|-|-|
|`>`|Greater than|
|`<`|Lesser than|
|`>=`|Greater than or equal to|
|`<=`|Lesser than or equal to|
|`==`|Equal|
|`!=`|Not equal|
- Objects also have a true or false value, and can be evaluated using `bool()`
### Logical operators
|Operator|Function|
|-|-|
|`and`|Both are true|
|`or`|Either one is true|
|`not`|If it is false, return true and vice-versa|
