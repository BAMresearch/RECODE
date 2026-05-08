# Code Quality and Good Practices

Writing code that works once is only the first step. In research settings,
clarity and reproducibility matter just as much as correctness.

## Reproducible code starts with small habits

Good research code should make it easy to answer questions such as:

- Which input data was used?
- Which parameters were chosen?
- Which environment was the code run in?
- Can someone else rerun this later?

You do not need a large framework to improve reproducibility. Small habits
already help a lot:

- keep scripts focused,
- use meaningful names,
- avoid hidden manual steps,
- write down assumptions near the code that depends on them.

## Style and readability

PEP 8 is the main Python style guide. The most important beginner takeaway is
simple: prefer readable code over clever code.

That usually means:

- short functions,
- descriptive variable names,
- consistent indentation,
- spaces around operators,
- blank lines to separate ideas.

## Docstrings and comments

Use docstrings to explain what a function is for:

```python
def load_measurements(path):
    """Load measurement data from a CSV file into a DataFrame."""
```

Use comments more sparingly. Good comments explain **why** something is done,
not just **what** the next line obviously does.

## Typing

Type hints make intent clearer and can support better editor tooling:

```python
from pathlib import Path

def load_text(path: Path) -> str:
    return path.read_text(encoding="utf-8")
```

You do not need to annotate everything from day one, but adding types to public
functions and important data flows is a good habit.

## Logging and errors

Avoid silent failures. If something goes wrong, your program should give useful
feedback.

```python
import logging

logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("Loading measurement data")
```

Combine this with clear exceptions when inputs are invalid or files are
missing.

## Testing

Tests are a way to protect expected behavior. Even a very small test can be
valuable:

```python
def calc_square(x):
    return x ** 2

def test_calc_square():
    assert calc_square(4) == 16
```

The lesson for Module 1 is not to master testing frameworks yet. It is to
start thinking in terms of verifiable behavior.

## Tools you may encounter

Later in the course or in real projects, you may see tools such as:

- `ruff` for style and linting,
- `mypy` for static type checking,
- `pytest` for automated tests.

You do not need all of them immediately, but it helps to know what problem each
tool is trying to solve.

## A practical checklist

Before sharing a script with someone else, ask:

1. Are the names understandable?
2. Are inputs and outputs obvious?
3. Can another person rerun it?
4. Does it fail clearly when something is wrong?
5. Is the code short enough to review comfortably?
