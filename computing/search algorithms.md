- A search algorithm is an algorithm that checks for the existence of an element, or to retrieve an element from any data structure where it is stored
- There is linear search and binary search
## Big-O notation
- Big O notation shows the time needed to execute a line of code
- Constants are dropped
- Every statement that operates on one item at once has a time complexity of O(1)
- A for loop looping thorough an array of `n` size has a time complexity of O(n)
- A nested for loop looping through an array of n size has a time complexity of O(n²)
## Linear search
- Linear search involves looping through each item in the array, and checking its value against the target value
- If it has reached the end of the array, and still has not found the value, it returns -1
- In the worst case, the target is present at the last index of the list, so the worst case complexity is O(n)
- Simple to implement and easy to understand
- Can be used if the array is sorted or not
- Can be used on arrays of any data types
- Suitable for small data sets
- Slow for large data sets
### for loop
```Python
def linear_search(x, target):
	for i in range(len(x)):
		if x[i] == target:
			return i
	return -1
```

```Pseudo
FUNCTION linear_searc(x:ARRAY, target:INTEGER) RETURNS INTEGER
	FOR i <- 0 TO length of x - 1
		IF target = x[i] 
			THEN
				RETURN i
		ENDIF
	ENDFOR i
	RETURN -1
ENDFUNCTION
```
### while loop
```Python
def linear_search(x, target):
	counter = 0
	while counter < len(x):
		if x[counter] == target:
			return counter
		counter += 1
	return -1
```
```Pseudo
FUNCTION linear_searc(x:ARRAY, target:INTEGER) RETURNS INTEGER
	counter <- 0
	WHILE counter < length of x
		IF x[counter] == target
			THEN
				RETURN counter
		counter <- counter + 1
	ENDWHILE
	RETURN -1
```
## Binary search
- Binary search is used in a **sorted** array by repeatedly dividing the search interval in half
- Uses the idea that the array is sorted to reduce the time complexity
1. Set the low index to the first element of the array and the last index to the last element of the array
2. Set the middle index to the average of the low and high indexes
	- If the element at the middle index is the target element, return the middle index
	- If the element at the middle index is more than the target element, set the high index to middle index - 1
	- If the element at the  middle index is lesser than the target element, set the low index to middle index + 1
3. Repeat step 2 until the target element is found or the search space is exhausted
- In the worst case, the element is in the first index, so the worst case time complexity is O(log n)
- Binary search is faster than linear search, especially for larger arrays
- The time complexity of linear search increases linearly, while the time complexity of binary search increases logarithmically
- But, the array must be sorted first, adding an additional O(n log n) time complexity for the sorting step to sort the array
### While loop
```Python
def binary_search(x, target):
	low = 0
	high = len(x)
	while high >= low:
		mid = (low + high) // 2
		if x[mid] == target:
			return mid
		elif x[mid] > target:
			high = mid -1
		else:
			low = mid + 1
	return -1
```
```Pseudo
FUNCTION binary_search(A: LIST, target: INTEGER) RETURNS INTEGER
	low <- 0
	high <- length of A
	WHILE low <= high DO
		mid <- (low + high) DIV 2
		IF target = A[mid]
			THEN
				RETURN mid
			ELSE
				IF TARGET > A[mid]
					THEN
						low <- mid + 1
					ELSE
						high <- mid - 1
				ENDIF
		ENDIF
	RETURN -1
ENDFUNCTION
```
### Recursion
```Python
def binary_search(x, target, low, high)
	if low > high:
		return -1
	mid = (low + high) // 2
	if x[mid] == target:
		return mid
	elif x[mid] > target:
		binary_search(x, target, low, mid - 1)
	else:
		binary_search(x, target, low, mid - 1)
```
```Pseudo
FUNCTION binary_search(A: LIST, target: INTEGER, low: INTEGER, high: INTEGER) RETURNS INTEGER
	IF low > high
		THEN
			RETURN -1
		ELSE
			mid <- (low + high) DIV 2
			IF A[mid] = target
				THEN
					RETURN mid
				ELSE 
					IF A[mid] > target
						THEN
							RETURN binary_search(x, target, low, mid - 1)
						ELSE
							RETURN binary_search(x, target, low, mid - 1)
					ENDIF
			ENDIF
	ENDIF
ENDFUNCTION
```
