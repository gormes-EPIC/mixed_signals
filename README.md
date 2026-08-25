# Mixed Signals

## Your Task
- Read input.txt — 25 lines, each meant to be a number: integers, floats, spelled-out words ("three", "seven"), or garbage.
- Parse every line into a number and sum them all
- Use try/except so bad lines are skipped
- Only recognize number words "one"–"ten"
- Print the total sum at the end

  
## Try/Except in Python

Python code can crash when something unexpected happens — a missing file, bad user input, dividing by zero. `try`/`except` lets you catch those errors and handle them gracefully instead of letting the program die.

### Basic structure

```python
try:
    # code that might fail
    number = int("banana")
except ValueError:
    # runs only if a ValueError happens
    print("That wasn't a valid number!")
```

Python runs the `try` block first. If an error occurs, it stops immediately and jumps to the matching `except` block instead of crashing.

### Catching specific errors

You can catch different error types separately, since they usually need different handling:

```python
try:
    with open("data.txt") as f:
        content = f.read()
except FileNotFoundError:
    print("File doesn't exist.")
except PermissionError:
    print("Not allowed to read this file.")
```

### Catch-all (use sparingly)

```python
except Exception as e:
    print(f"Something went wrong: {e}")
```

This catches *any* error, which is handy as a safety net but can hide bugs if overused — it's usually better to catch specific exceptions when you know what might go wrong.

### Optional extras

```python
try:
    risky_thing()
except ValueError:
    print("Bad value")
else:
    print("Ran fine, no errors")   # only if try succeeded
finally:
    print("This always runs")     # cleanup, runs no matter what
```

**Rule of thumb:** only wrap the specific lines that might fail, and catch the specific error you expect — this keeps bugs from hiding behind a broad `except`.
