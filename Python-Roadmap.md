# Python Roadmap

## Basic Syntax

## types and Variables

## `if` statements

- if
- elif
- else
- finally?

## Loops

- while loops
- for loops
- `break` and `continue`
  - `break` cuts the loop off.
  - `continue` restarts it
- `else` statement
  - After a loop you can have an `else`-statement with a code block that executes if the loop finnishes without using `break`.

## Functions

```python
def greeting(name):
    print("Hello", name + "!")
    return None
```

## Modules

- `import module as m`
  - It basically runs a python file
    - This can result in functions and classes being defined so they can be used later in the main file.

## Type hinting

```python
def multiplication(num_1: int, num_2: int) -> int:
    return num_1 * num_2

def print_multiplied(print_list: list, multiply_list: list(int)) -> None:
    for index, value in enumerate(print_list):
        for i in range(multiply_list[index]):
            print(value)
```
