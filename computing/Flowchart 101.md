## The 6 elements of a flowchart

![[Flowchart elements.png]]

## Example
```python
def func():
	n = int(input())
	while n > 0:
		print(n)
		n -= 1
```
```
PROCEDURE func
	DECLARE n: Integer
	INPUT n
	WHILE n > 0
		OUTPUT n
		n ← n - 1
	ENDWHILE
ENDPROCEDURE
```

![[Flowchart examples.png]]

- Flowchart lines should never cross
- There are no for loops in flowchart
- Decisions need to have True and False values
## Selection constructs
![[Flowchart for selection constructs.png]]
## While loops
![[Flowchart for while loop.png]]
## For loops
![[Flowchart for for loop.png]]