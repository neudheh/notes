#computing 
- There are 4 data types in Python:
	1. Integers (`int`)
	2. Floating Point value(`float`)
	3. String (`str`)
	4. Boolean (`bool`)
- There is also a special `None` Value that is used to keep track that a value is missing or there are no suitable values to be assigned to the variable (e.g. the variable represents an optional input)
# Type casting
- Type casting is converting a value form one type to another
- Use the python name of the value like a function (e.g. `int(12.3)` converts the floating point value of 12.3 into an integer, and `str(x)` converts the variable value of x into a string)
# Integers
- Integers (known as `int`) are positive and negative whole numbers, including zero
- The literal format for Python is just the digits written out with a possible negative sign in front
- Have no limit, positive or negative, in the whole numbers they can represent
# Arithmetic operators
|Operator|Name|Description|Examples|
|-|-|-|-|
|+|Addition|Returns the sum of two values|`print(9+4)` (Output: 13)|
|-|Subtraction|Returns the difference of two values|`print(9-4)` (Output: 5)|
|* |Multiplication|Returns the product of two values|`print(9*4)` (Output: 36)|
| /|Division|Returns the value on the left divided by the value on the right| `print(9/4)` (Output: 2.25)|
|//|Floor division|Returns the value on the left divided by the value on the right, rounded down to the nearest integer|`print(9//4)` (Output: 2)|
|%|Modulus (Remainder)|Returns the remainder when the value on the left is divided by the value on the right|`print(9%4)`(Output:1)|
|\*\*|Exponentaion (Power)|Returns the value on the left raised to the power of the value on the right|`print(9**4)` (Output: 6561)|
- Applying most operators on two ints usually results in two ints, but the division operator always results in a float
- Modulus operator is particularly useful for determining if a number is even or odd
	- If `x%2` returns 1, the number is odd, else if it returns 0, the number is even
- We often need to use a variable for a calculation, and then update the value with the result
- For convenience, Python provides us with assignment operators to help save some typing when doing this task

|Operator|Example|Equivalent|
|-|-|-|
|`+=`|`x += a`|`x = x + a`|
|`-=`|`x -= a`|`x = x - a`|
|`*=`|`x *= a`|`x = x * a`|
|`/=`|`x /= a`|`x = x / a`|
|`//=`|`x //= a`|`x = x // a`|
|`%=`|`x %= a`|`x = x % a`|
|`**=`|`x **= a`|`x = x ** a`|
# Floating point value
- A floating point value, or a `float` is a real number
- Can be written as
	- Digits of the float with the decimal point included explicitly (e.g. `123.4`)
	- The form AeB or AEB to represent $A * 10^ b$ (e.g. `1.234e2`)
- Due to the way they are stored, floats are not especially accurate
- The most positive and negative values a float can have are approximately $1.79 *10^{308}$ and$-1.79 *10^{308}$ respectively
- Beyond that, the float will be converted to the special values of infinity (`inf` or `-inf`)
- When casting a `float` to an `int`, the conversion is done by truncating all digits after the decimal point (i.e. `int(8.9)` returns 8, `int(-8.9)` returns -8)
- The same arithmetic integers that work for integers work for floats too
# Strings
- A string, or an `str` is used to represent text
- It consists of contents enclosed by single-quotes (') or double quotes (") (e.g. "Hello World!", 'Computing wow')
- Sometimes, strings may contain characters that are difficult to type out as a part of a literal or would cause a syntax error if not treated specially
- Hence, we have escape codes, which can by typed with the backslash key (\\) and the escape code
|Escape code| Meaning|
|-|-|
|`\\`|Backslash (\\)|
|`\'`|Single-Quote (')|
|`\"`|Double-Quote(")|
|`\n`|Newline Character|
|`\t`|Tab character|
- 
## Methods
# Booleans
