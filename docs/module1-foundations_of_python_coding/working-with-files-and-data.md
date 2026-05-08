# Working with Files and Data

This part of Module 1 connects basic Python syntax with the kind of tasks many
researchers actually do: finding files, reading data, transforming it, and
visualizing results.

## Files and folders

The notebook material in `module1s5/` starts with a useful question:

> From which folder is this script or notebook running?

That matters because relative paths depend on the current working directory.

With `pathlib`, you can inspect the filesystem clearly:

```python
from pathlib import Path

current_dir = Path.cwd()
print(current_dir)

for path in current_dir.iterdir():
    print(path.name)
```

## Filtering files

When a folder contains many files, you often want only a subset:

```python
from pathlib import Path

csv_files = list(Path.cwd().glob("*.csv"))
print(csv_files)
```

This is a simple but important step toward automation. Instead of opening files
manually one by one, your code can discover them for you.

## Reading and writing common file types

### Text files

```python
from pathlib import Path

text = Path("notes.txt").read_text(encoding="utf-8")
print(text)
```

### JSON

```python
import json
from pathlib import Path

data = json.loads(Path("config.json").read_text(encoding="utf-8"))
print(data["project_name"])
```

### CSV with pandas

```python
import pandas as pd

df = pd.read_csv("measurements.csv")
print(df.head())
```

## Arrays with NumPy

NumPy is the standard tool for fast numerical arrays and vectorized
calculations:

```python
import numpy as np

angles = np.linspace(0.01, 5.0, 500)
values = np.sin(angles)
```

Vectorized code is one of Python's biggest strengths in scientific workflows:
you can apply one operation to many values at once.

## Plotting with matplotlib

Visualization is often the fastest way to understand data:

```python
import matplotlib.pyplot as plt

plt.plot(angles, values)
plt.xlabel("angle")
plt.ylabel("signal")
plt.grid()
plt.show()
```

The introductory notebook in `module1s2/` also uses small plotting examples to
show how quickly Python can move from values to visual feedback.

## Structured data with pandas

Pandas is especially useful when working with tables:

```python
import pandas as pd

df = pd.DataFrame(
    {
        "sample": ["A", "B", "C"],
        "intensity": [10.2, 12.5, 9.8],
    }
)

print(df)
print(df["intensity"].mean())
```

Typical pandas tasks include:

- filtering rows,
- selecting columns,
- grouping by categories,
- merging data from multiple sources,
- exporting cleaned results.

## From loading data to modeling

The optional notebook in `module1s5/` goes one step further and shows how
loaded data can feed into:

- computed `Q` vectors,
- mathematical models,
- plots on linear or logarithmic scales,
- parameter fitting with scientific libraries.

That notebook is a good example of how Module 1 begins with basics but already
points toward realistic scientific coding tasks.

## Good habits when working with data files

- Keep raw data unchanged and write processed results separately.
- Use clear filenames and folder names.
- Prefer `pathlib` over fragile hand-written path strings.
- Check shapes, columns, and units early.
- Plot intermediate results when something looks suspicious.

## Practice ideas

1. List all `.csv` files in a folder.
2. Read one file into pandas and print the first five rows.
3. Create a NumPy array with evenly spaced values.
4. Plot one column against another with labels on both axes.
