# Python Cheatsheet
Just some python basics.

### Variables
Define a variable like:
```
x = 12
```

### Functions
Define a function like
```python
def someFunction(param):
	'some descriptive text'
	print(param)
	return True
```

### Helpful built in functions
* `len('hey')` or `len(['h','e','y']) # => 3`
* `''.join(['h','e','y']) # => 'hey'`
* `for index, value in enumerate(list): # to get index`

### Arguments
* Argument lists - traditional to name it args. Write it like this: `def function(*args)`
* Keyword arguments - two asterisks like `def function(**kwargs)`. Same syntax as dictionary. These are named arguments, like `function(Buffy = 'meow', Zilla = 'grr')`

### Generator Function
- Instead of returning a single value like a normal function, it returns a stream of values. Useful for creating a series of values.
- Use the keyword `yield` to return a value and then continue the function. Useful in loops to return a value at each loop, for example

### Decorator
- A special type of function that returns a wrapper function. Syntax looks like this:

```python
def sayHey(fn):
	def wrapper():
		print('hey!')
		fn()
	return wrapper

@sayHey
def sayHeyAndBye():
	print('bye!')

sayHeyAndBye()
```
Basically, @sayHey wraps around the following function definition `sayHeyAndBye` and `sayHeyAndBye()` becomes the returned wrapper of `sayHey` like a curried function in JavaScript


### Structured Data
- List - mutable, can add, delete and change values, with brackets. Like an array in JavaScript. `[1, 2, 3, 4, 5]`
- Tuple - like a list, but immutable. Uses parentheses like `(1, 2, 3, 4, 5)`
- Dictionary - sequence of key/value pairs. Like `{ 'a': 1, 'b': 2', 'c': 3}`
- Set - unordered list of unique values. Useful for finding and operating upon unique values within a sequence. `x = { 1, 2, 3, 4, 5}`

- Lists - can access index same way as range. Like
```python
x = ['Rock', 'Paper', 'Scissors', 'Lizard', 'Spock']
x[1:5:2] # => [ 'Paper', 'Lizard']
```

List Comprehensions are like array.map in JavaScript. You can iterate over a list and do work on each entry like this:
```python
seq = range(11)
seq2 = [x * 2 for x in seq]
seq3 = [(x, x**2) for x in seq]
seq4 = [round(pi, x) for x in seq]
seq5 = { x: x**2 for x in seq}
seq6 = { x for x in 'superduper' if x not in 'pd'}
```
