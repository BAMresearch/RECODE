# Python Basics

Python is widely used because it is readable, versatile, and supported by a
large ecosystem of scientific and general-purpose libraries. In RECODE, we use
it as the common language for examples, exercises, and small research tools.

## Ways to run Python

You will encounter Python in three common forms:

- **Interactive terminal** for quick experiments,
- **scripts** for repeatable code stored in `.py` files,
- **notebooks** for teaching, exploration, and mixed text/code workflows.

Each one is useful. What matters is recognizing when to use which format.

## Variables and names

Variables store values so you can reuse them later:

```python
temperature_c = 23.5
sample_name = "alloy_A"
is_valid = True
```

Choose names that describe the meaning of the value, not just its type.
`sample_name` is better than `x`, and `is_valid` is better than `flag1`.

## Basic data types

Some common Python data types are:

- `str` for text,
- `int` for whole numbers,
- `float` for decimal numbers,
- `bool` for `True` / `False`,
- `complex` for complex numbers.

You can inspect a value's type with:

```python
value = 3.14
print(type(value))
```

## Expressions and operators

Python follows standard mathematical rules for many operations:

```python
3 + 4
3 ** 4
2 + 3 - 4 * 5 / 2
```

Parentheses help make intent explicit:

```python
a = 3 ** 4
result = a * (3 + 4 * (5 + 6))
```

## Functions

Functions let you name a reusable action:

```python
def calc_square(x):
    return x ** 2
```

You can then call the function with different inputs:

```python
print(calc_square(5))
print(calc_square(12))
```

Functions are one of the first major steps from "typing commands" to "writing
programs."

## Module imports

Importing further modules extend the functionality.
[Python's standard library](https://docs.python.org/3/py-modindex.html) already contains many helpful tools:

```python
import math

print(math.sqrt(81))
```

External libraries, such as [NumPy](https://numpy.org/doc/stable/user/whatisnumpy.html), add more capabilities:

```python
import numpy

print(numpy.sinc(49))
```

This is a common pattern in scientific Python: start with core language
features, then bring in specialized libraries when the problem requires them.

## Notebooks as a learning tool

The introductory notebook in the repository shows a useful teaching pattern:

- write a small code cell,
- run it immediately,
- inspect the result,
- modify one thing and run it again.

That feedback loop is especially effective when learning basics such as:

- printing values,
- checking data types,
- comparing lists and arrays,
- plotting simple results.

## Practice ideas

Try the following on your own:

1. Create three variables with different types.
2. Write a function that converts Celsius to Kelvin.
3. Import `math` and calculate a square root.
4. Print a sentence that includes both text and a number.

The point is not complexity. The point is building fluency with the syntax.
