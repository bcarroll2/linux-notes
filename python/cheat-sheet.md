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

### Classes
like so:
```python
class Duck:
	# Class Variables - these are public (like donald.sound is valid)
	# and apply to all instances of the class
	sound = 'Quack'
	
	def __init__(self, **kwargs):
		# underscore to denote "private" (but not really)
		self._type = kwargs['type'] if 'type' in kwargs else 'Mallard'
		self._name = kwargs['name']
		self._sound = kwargs['sound']

	# method
	def quack(self):
		# instance is always first arg, traditionally
		# referenced by `self`
		print(self.sound)

	# Getter
	def name(self, name = None):
		if name: self._name = name
		return self._name

	# Specially named function that prints this line when
	# print(objectInstance) is called
	__str__(self):
		return f'This object's name is {self.name()}'

# an instance of Duck, also called an object
donald = Duck(type='Cartoon', name='Donald', sound='quack')


```
Class inheritance can be done by passing a class as an argument to another class like:

```python
class MySuperClass:
	def __init__(self, **kwargs)"
		if 'type' in kwargs: self._type = kwargs['type']
		if 'name' in kwargs: self._name = kwargs['name']
	
	def type(self, type = None):
		if type: self._type = type
		try: return self._type
		except AttributeError: return None

	def name(self, name = None):
		if name: self._name = name
		try: return self._name
		except AttributeError: return None

class MySubClass(MySuperClass):
	def __init__(self, **kwargs):
		self._type = 'SubClass'
		# If type was passed in, delete it because
		# the type is hard coded in this subclass
		if 'type' in kwargs: del kwargs['type']
		# Call the parent class with the remaining args
		super().__init__(**kwargs)

```
### Iterators
An iterator is a class that provides a sequence of items generally used in a loop.
Iterators are functionally the same as generators, which are a bit eaier to implement.
