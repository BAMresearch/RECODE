# Control Flow and Data Structures

Once you can assign values and write functions, the next step is telling Python
how to make decisions, repeat work, and organize collections of data.

## Conditionals

Use conditionals when your program should behave differently depending on a
value:

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

## Lists, tuples, dictionaries, and sets

Python has several built-in data structures, each with a different purpose.

### Lists

Lists store ordered, changeable collections:

```python
samples = ["steel", "glass", "polymer"]
samples.append("ceramic")
```

### Tuples

Tuples also store ordered values, but they are typically used for fixed groups
of values:

```python
dimensions = (12.0, 4.0, 1.5)
```

### Dictionaries

Dictionaries map keys to values:

```python
metadata = {
    "sample_id": "A-17",
    "temperature_c": 23.5,
    "operator": "BAM",
}
```

They are useful whenever labels matter as much as the values themselves.

### Sets

Sets store unique values and are useful for quick membership tests:

```python
elements = {"Fe", "C", "Mn"}
```

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

## List comprehensions

List comprehensions are a compact way to build a list from another iterable:

```python
numbers = [1, 2, 3, 4]
squares = [n ** 2 for n in numbers]
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
