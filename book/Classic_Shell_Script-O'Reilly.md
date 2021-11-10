# Classic Shell Script - O'Reilly

Table of Contents
=================

# Context

## Chapter 02 - Basic of shell
- Command and argument
    - Shell command type
        - Built-in command (e.g. echo)
        - Shell function (e.g. function in regular programs)
        - External function
            - Executed by forked child shell instead of original parent shell
    - Argument
- Variable
- Print message
    ```bash
    # Simple output
    echo "hello world" # >> hello world
    # Formatted output
    printf "%s, %s!" hello world # >> hello, world!
    ```
- Standard I/O (input/output) manipulation
    - Redirect standard input (<)
    - Redirect standard output (>)
    - Append standard output to (>>)
    - Pass previous standard output as next standard input (|)
- Special file
    - /dev/null
        - Message directed to null would not be stored in system
    - /dev/tty
        - Output will be redirected to a virtual terminal

## Chapter 03 - Search and substitution
- Regular expression
    - POSIX expression
- Shell tool for search and substitution
    - sed
    - cut
    - join
    - awk

## Chapter 04 - Text tool
- Shell tool for text file
    - sort
    - uniq
    - wc

## Chapter 06 - Variables, conditional expression, and loop
- Set variable
    - export
        - Create shell variable
            ```bash
            # Set shell variable
            export TEST=test

            # Print out all shell variables
            export -p
            ```
    - readonly
        - Create shell variable but readonly
    - unset
        - Remove shell variable
- Parameter expansion
- Conditional expression
- Case
    - Shift
- Loop
    - For loop
    - While loop
        - Break
        - Continue
    - Until loop
