# Data Structures and Control Flow

Once you can assign values and write functions, the next step is telling Python
how to make decisions, repeat work, and organize collections of data.

## Lists, tuples, sets and dictionaries

Python has several built-in data structures, each with a different purpose.
More details can be found in the excellent
[Python Standard Library Documentation on sequences](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range)

### Lists

[Lists](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range) store ordered, changeable collections:

```python
samples = ["steel", "glass", "polymer"]
samples.append("ceramic")
print(samples)
    ['steel', 'glass', 'polymer', 'ceramic']
samples[2] = "silica"
print(samples)
    ['steel', 'glass', 'silica', 'ceramic']
```

For sequences, such as lists and tuples, individual elements can be selected, called *indexing*.
Indices always start at 0: The first element always has the index 0.
The last element can be chosen by using a negative index which counts from the end: -1 is the last element.

```python
print(samples[0])
    steel
print(samples[-1])
    ceramic
```

Also, sub-ranges can be selected with two indices and a colon ':' called *slicing*.
The specified indices define the first element to include until the element specified by the second index, but not including it!

```python
print(samples[1:3])
  ['glass', 'silica']
```

### Tuples

[Tuples](https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range) also store ordered values, but they are typically used for fixed groups of values (read-only):

```python
dimensions = (12.0, 4.0, 1.5)
```

This will give an error:

```python
dimensions[1] = 3
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
```

The above tuple can only be changed by composing a new tuple using the '+' operator:

```python
dimensions[:1] + (3,) + dimensions[2:]
(12.0, 3, 1.5)
```

Where `(3,)` is a tuple with a single element and `dimensions[:1]` indicates a slice of the *dimensions* tuple from the beginning until the first element (but not the second which has index 1). While `dimensions[2:]` will give a slice of the tuple from the third element (index 2) until the end.

### Strings

Coming back to strings for a moment, since they behave like tuples of characters in Python.

```python
text = "Hello World"
text[3:9]
    'lo Wor'
```

Strings also can not by changed directly but need to be rebuild:

```python
text[:5] + "-" + text[6:]
    'Hello-World'
```

**Note:** Sometimes, trouble may be caused by strings accidentally used with code designed for sequences:
It will often just work but will not give the expected result.
We come back to that later, after *loops*.

### Sets

[Sets](https://docs.python.org/3/library/stdtypes.html#set-types-set-frozenset) store unique values (no duplicates can exist) and are useful for quick membership tests:

```python
elements = {"Fe", "C", "Mn"}
"Fe" in elements
    True
```

They are very close to sets in the math and support operations like [*intersection*, *union* and *difference*](https://docs.python.org/3/library/stdtypes.html#frozenset.issuperset).

### Dictionaries

[Dictionaries](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)
map keys to values, also called *associative arrays* in computer science. They are very powerful and widely used in Python:

```python
metadata = {
    "sample_id": "A-17",
    "temperature_c": 23.5,
    "operator": "BAM",
}
```

They are useful whenever labels matter as much as the values themselves.
They can be modified and keep the order of items as they were added.
Dictionaries can have unique keys only, same as a set and in contrast to lists and tuples which may have many duplicate elements.

## Conditionals

Use conditionals when your program should behave differently depending on a value:

```python
temperature = 18

if temperature < 0:
    print("Freezing")
elif temperature < 20:
    print("Cool")
else:
    print("Warm")
```

This pattern appears everywhere: validating inputs, checking files, handling
errors, and controlling workflow.

## Loops

Loops let you repeat an operation.

### `for` loops

Use `for` when iterating over a sequence:

```python
for sample in samples:
    print(sample)
```

### `while` loops

Use `while` when repetition depends on a condition:

```python
count = 0

while count < 3:
    print(count)
    count += 1
```

### Pitfall: accidentally treat a string as a sequence of items

```python
def print_items(items):
    for item in items:
        print(item)

# Intended usage:
print_items(["apple", "banana", "cherry"])
```
Now accidentally pass a string:

```python
print_items("apple")
a
p
p
l
e
```

**Why this happens:**
- A string is a sequence of characters
- The loop iterates over each character instead of treating "apple" as one item
- Fix: use [isinstance()](https://docs.python.org/3/library/functions.html#isinstance)

```python
def print_items(items):
    if isinstance(items, str):
        items = [items]  # treat as single item
    for item in items:
        print(item)
```

## List comprehensions

List comprehensions are a compact way to build a list from another iterable:

```python
numbers = [1, 2, 3, 4]
squares = [n ** 2 for n in numbers]
squares
    [1, 4, 9, 16]
```

They are powerful, but clarity still matters. If a comprehension becomes hard
to read, a normal loop is often the better choice.

## Error and exception handling

Real code should fail in understandable ways. A basic `try` / `except`
structure helps:

```python
try:
    value = int("42")
except ValueError:
    print("Conversion failed")
```

Use exception handling to react to expected failure modes, such as invalid
input, missing files, or parsing problems.

## Recursion

Recursion means a function calls itself. It is useful for some problems, but it
is not always the clearest choice for beginners:

```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n - 1)
```

It is worth understanding the idea, even if loops remain the more common tool
in daily work.

## Practice ideas

1. Create a list of numbers and print only the even ones.
2. Build a dictionary that stores a few measurements by name.
3. Write an `if` / `elif` / `else` block for a grading scale.
4. Convert a `for` loop into a list comprehension and compare readability.
