# Missing Semester - Lecture 07 - Debugging and Profiling

- Reference
  - [Course_youtube_link](https://www.youtube.com/watch?v=l812pUnKxME)
  - [Course_webpage_resources](https://missing.csail.mit.edu/2020/debugging-profiling/)

# Table of Contents

- [Missing Semester - Lecture 07 - Debugging and Profiling](#missing-semester---lecture-07---debugging-and-profiling)
  - [Table of content](#table-of-content)
  - [Context](#context)
    - [Log](#log)
    - [Debugger](#debugger)
    - [Profiling](#profiling)

Created by [gh-md-toc](https://github.com/ekalinin/github-markdown-toc)

# Context

## Log

Track command/function that has has run

- System log in unix-like System

  ```bash
  #_Print out all system log
  journalctl
  ```

## Debugger

Print out detailed error message for debugging

- Python debugger

  - Ipython debugger (interactive debugger)

    - Pretty color log support

    ```bash
    #_In terminal
    python -m ipdb <file_to_be_tested>

    #_In interactive mode of ipdb
    #_q: quit debugger
    #_l: list all lines
    #_s: step by step (line by line) execution
    #_c: continue till confronting next bug
    #_b <LINE_NUMBER>: create break point at specific line
    #_p: print out variable value
    #_p locals(): print out all current local variables
    ```

- Binary debugger

  - GDB
    - Print low level informations

- Specialized tools

  - Strace
    - Print out system calls

- Static analysis tools

  - To check syntax error quickly
  - For python code

## Profiling

Profile time/CPU/memory usage used to execute functions to optimize your code efficiency

- Shell profiler

  - Time profiler

    ```bash
    time <function_to_be_profiled>
    ```

  - Visualizer

    - Flame graph

  - Resource monitoring

    - top
    - htop (interactive version of top)

  - Storage monitoring

    - du
    - ncdu (interactive version of du)

  - Compare efficiency of two commands/functions

    ```bash
    #_hyperfine
    hyperfine --warmup 3 <command_1> <command_2>
    ```

- Python profiler

  - Time profiler

    ```bash
    #_In python script
    #_Add decorator @profile in the head of function (above def)

    #_e.g.
    #_@profile
    #_def test_function():

    #_In terminal
    kernprof -l -v <python_script>
    ```

  - Memory profiler

    ```bash
    #_In python script
    #_Add decorator @profile in the head of function (above def)

    #_e.g.
    #_@profile
    #_def test_function():

    #_In terminal
    python -m memory_profiler <python_script>
    ```

  - Visualizer

    - pycallgraph
