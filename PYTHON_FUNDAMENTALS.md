# Python Fundamentals 

## Variables 

- Variable names can only contain these characters:
  * Lowercase letters (a through z)
  * Uppercase letters (A through Z)
  * Digits (0 through 9)
  * Underscore (_)
- Names cannot begin with a digit.

## Data Types

In Python, everything — booleans, integers, floats, strings, even large data structures, functions, and programs—is implemented as an object.

- Integers (1, 3, -10)
 
> Python 2.x `int` has 32 bit precision, `long` has 64 bit precision. In Python 3 `long` no longer exists, `int` can be any size

- Floats (45.2)
- Booleans (True, False)
- Strings ('Hello', "Hi")

### Working with Strings

#### String concatenation 

```python
"Hi, my name is " + "Joe"
```

#### Duplication 

```python
"Hello" * 4
```

#### Extraction 

```python
letters = 'abcdefghijklmnopqrstuvwxyz'
letters[0] 
# 'a'
```

#### Slicing

* [:] extracts the entire sequence from start to end.
* [ start :] specifies from the start offset to the end.
* [: end ] specifies from the beginning to the end offset minus 1.
* [ start : end ] indicates from the start offset to the end offset minus 1.
* [ start : end : step ] extracts from the start offset to the end offset minus 1, skipping characters by step.

```python
letters = 'abcdefghijklmnopqrstuvwxyz'

letters[:]
# 'abcdefghijklmnopqrstuvwxyz'

letters[20:]
# 'uvwxyz'

letters[12:15]
# 'mno'

letters[-3:]
# 'xyz'
```

#### Length

```python
letters = 'abcdefghijklmnopqrstuvwxyz'
len(letters)
# 26
```

#### Split 

```python
todos = 'get gloves,get mask,give cat vitamins,call ambulance'
todos.split(',')
# ['get gloves', 'get mask', 'give cat vitamins', 'call ambulance']
```

#### Capitalize

```python
setup = 'a duck goes into a bar...'

setup.strip('.')
# 'a duck goes into a bar'

setup.capitalize()
# 'A duck goes into a bar...'

setup.upper()
# 'A DUCK GOES INTO A BAR...'

setup.lower()
# 'a duck goes into a bar...'

setup.replace('duck', 'marmoset')
# 'a marmoset goes into a bar...'
```

## None

`None` - The equivalent of the `null` keyword in other languages

## Operators 

* `+` Addition 
  - `5 + 8 = 13`
* `-` Subtraction 
  - `90 - 10 = 80`
* `*` Multiplication 
  - `4 * 7 = 28`
* `/` Floating point division 
  - `7 / 2 = 3.5`
* `//` Integer (truncating) division 
  - `7 // 2 = 3`
* `%` Modulus (remainder) 
  - `7 % 3 = 1`
* `**` Exponentiation 
  - `3 ** 4 = 81`
  
## Lists

Lists are good for keeping track of things by their order, especially when the order and
contents might change. Unlike strings, lists are mutable. You can change a list in-place,
add new elements, and delete or overwrite existing elements. The same value can occur
more than once in a list.

```python
weekdays = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday']
empty_list = list()
```

```python
list('cat')
# ['c', 'a', 't']

a_tuple = ('ready', 'fire', 'aim')
list(a_tuple)
# ['ready', 'fire', 'aim']

birthday.split('/')
# ['1', '6', '1952']
```

#### Get Number of Elements

```python
marxes = ['Groucho', 'Chico', 'Harpo']
len(marxes)
# 3
```

#### Obtaining an Element

```python
marxes = ['Groucho', 'Chico', 'Harpo']
marxes[0]
# 'Groucho'
```

#### Lists of Lists

```python
small_birds = ['hummingbird', 'finch']
extinct_birds = ['dodo', 'passenger pigeon', 'Norwegian Blue']
carol_birds = [3, 'French hens', 2, 'turtledoves']
all_birds = [small_birds, extinct_birds, 'macaw', carol_birds]

all_birds
# [['hummingbird', 'finch'], ['dodo', 'passenger pigeon', 'Norwegian Blue'], 'macaw', [3, 'French hens', 2, 'turtledoves']]

all_birds[0]
# ['hummingbird', 'finch']

all_birds[1][0]
# 'dodo'
```

#### Slicing

```python
marxes = ['Groucho', 'Chico,' 'Harpo']
marxes[0:2]

# ['Groucho', 'Chico']

marxes[::-2]
# ['Harpo', 'Groucho']

# Trick to reverse a list
marxes[::-1]
# ['Harpo', 'Chico', 'Groucho']
```

#### Add an Item 

```python
marxes.append('Zeppo')
# ['Groucho', 'Chico', 'Harpo', 'Zeppo']
```

#### Combining Lists

```python
marxes = ['Groucho', 'Chico', 'Harpo', 'Zeppo']
others = ['Gummo', 'Karl']
marxes.extend(others)
# ['Groucho', 'Chico', 'Harpo', 'Zeppo', 'Gummo', 'Karl']

# Alternatively: 
marxes = ['Groucho', 'Chico', 'Harpo', 'Zeppo']
others = ['Gummo', 'Karl']
marxes += others
# ['Groucho', 'Chico', 'Harpo', 'Zeppo', 'Gummo', 'Karl']
```

#### Test for Value

```python
marxes = ['Groucho', 'Chico', 'Harpo', 'Zeppo']
'Groucho' in marxes
# True
```

#### Convert to String

```python
marxes = ['Groucho', 'Chico', 'Harpo']
', '.join(marxes)
# 'Groucho, Chico, Harpo'
```

#### Sorting

```python
marxes = ['Groucho', 'Chico', 'Harpo']
sorted_marxes = sorted(marxes)

# ['Chico', 'Groucho', 'Harpo']
```

## Tuples

Similar to lists, tuples are sequences of arbitrary items. Unlike lists, tuples are immutable,
meaning you can’t add, delete, or change items after the tuple is defined. So, a tuple
is similar to a constant list.

```python
empty_tuple = ()
```

```python
marx_tuple = 'Groucho', 'Chico', 'Harpo'
print(marx_tuple)
# ('Groucho', 'Chico', 'Harpo')
```

```python
marx_tuple = ('Groucho', 'Chico', 'Harpo')
a, b, c = marx_tuple
print(a)
# 'Groucho'
print(b)
# 'Chico'
print(c)
# 'Harpo'
```

## Dictionaries

A dictionary is similar to a list, but the order of items doesn’t matter, and they aren’t
selected by an offset such as 0 or 1. Instead, you specify a unique key to associate with
each value. This key is often a string, but it can actually be any of Python’s immutable
types: boolean, integer, float, tuple. 

```python
empty_dict = {}
```

#### Obtain Item by Key

```python
pythons = {
 'Chapman': 'Graham',
 'Cleese': 'John',
 'Idle': 'Eric',
 'Jones': 'Terry',
 'Palin': 'Michael',
}

pythons['Cleese']
# 'John'
```

#### Add or Change Item by Key

```python
pythons['Gilliam'] = 'Gerry'
print(pythons)

# {'Cleese': 'John', 'Gilliam': 'Gerry', 'Palin': 'Michael', 'Chapman': 'Graham', 'Idle': 'Eric', 'Jones': 'Terry'}
```

#### Delete Item by Key

```python
del pythons['Marx']
```

#### Delete all Keys

```python
pythons.clear()
# {}
```

#### Test for Existence of Key

```python
'Chapman' in pythons
# True
```

## Conditionals

```python
color = "puce"

if color == "red":
  print("It's a tomato")
elif color == "green":
  print("It's a green pepper")
elif color == "bee purple":
  print("I don't know what it is, but only bees can see it")
else:
  print("I've never heard of the color", color)
```

### Falsy Values

* boolean `False`
* null `None`
* zero integer `0`
* zero float `0.0`
* empty string `''`
* empty list `[]`
* empty tuple `()`
* empty dict `{}`
* empty set `set()`

## For Loops

```python
rabbits = ['Flopsy', 'Mopsy', 'Cottontail', 'Peter']
for rabbit in rabbits:
  print(rabbit)
```

```python
cheeses = []
for cheese in cheeses:
  print('This shop has some lovely', cheese)
  break
else:
  print('This is not much of a cheese shop, is it?')
```

## Range

You use range() similar to how to you use slices: range( start, stop, step ). If you
omit start, the range begins at 0. The only required value is stop; as with slices, the
last value created will be just before stop. The default value of step is 1, but you can go
backward with -1.

```python
for x in range(0,3):
  print(x)
# 0
# 1
# 2

list( range(0, 11, 2) )
# [0, 2, 4, 6, 8, 10]
```

## Comprehensions

A comprehension is a compact way of creating a Python data structure from one or more
iterators.

### List Comprehensions

```python
number_list = []
for number in range(1, 6):
  number_list.append(number)

print(number_list)
# [1, 2, 3, 4, 5]
```

The simplest form of list comprehension is: `[ expression for item in iterable ]`
