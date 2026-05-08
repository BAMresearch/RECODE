# Introduction to Object-Oriented Programming

Object-oriented programming (OOP) is one way to organize code when data and the
operations on that data belong closely together.

## What is a class?

A class is a blueprint for creating objects:

```python
class Measurement:
    def __init__(self, sample_name, value):
        self.sample_name = sample_name
        self.value = value

    def is_valid(self):
        return self.value >= 0
```

You can create instances from the class:

```python
m = Measurement("sample_A", 12.4)
print(m.sample_name)
print(m.is_valid())
```

## Core vocabulary

- A **class** defines structure and behavior.
- An **object** or **instance** is one concrete result of that class.
- An **attribute** stores data on the object.
- A **method** is a function that belongs to the object.

## Why use OOP?

OOP is useful when:

- several values belong together naturally,
- the same operations apply repeatedly to similar entities,
- you want to represent real concepts such as samples, instruments, or models.

For example, a `Measurement`, `Experiment`, or `Spectrum` can often be modeled
cleanly as an object.

## Abstraction

Abstraction means presenting a simpler interface while hiding lower-level
details. A good class lets the user focus on what the object does, not on every
implementation detail.

That does **not** mean every piece of code needs to become a class. Sometimes a
simple function is the better design.

## OOP vs. functional style

In practice, Python projects often use a mix:

- **functions** for straightforward transformations,
- **classes** for stateful or domain-oriented structures.

Module 1 should leave students with a balanced intuition:

- use classes when they make the model clearer,
- avoid classes when they only add ceremony.

## Design habits for beginners

- Keep classes small.
- Give methods one clear purpose.
- Prefer meaningful names over generic ones like `DataManager`.
- Start simple before thinking about inheritance or advanced patterns.

## Practice idea

Create a class for a measurement series that stores:

- a sample name,
- a list of values,
- a method that returns the average value.

That exercise is enough to practice attributes, methods, and basic design
without making OOP feel heavier than it needs to be.
