# Python Debugger

## PDB

### Usage

- Interactive

  - In Command Line

    ```python
    python -m pdb <FILE.PY>
    ```

  - In Python Code

    ```python
    # For python >= 3.7
    ...

    breakpoint()
    ...
    ```

- Non-interactive (logging without interactive debugging)

  - In Python Code

    ```python
    pdb.runcall(FUNCTION, *args, **kwargs)

    ```

### Commands

- l (list): Displays the code around the current line.
- n (next): Moves to the next line of code, staying within the current function.
- s (step): Steps into the function call.
- c (continue): Continues execution until a breakpoint is encountered.
- q (quit): Quits the debugger.
- p (print): Print the value of an expression, like variables.

### Advanced

- whatis: Print type of the argument
- w (where): Display current location
- up: Navigate to the caller (parent function) frame.
- down: Navigate back to the current or called (child function) frame.
