- __Tags__: #Concurrency #Synchronous #Asynchronous #Thread #Process #Coroutine
- __Vimwiki__: :Concurrency:Synchronous:Asynchronous:Thread:Process:Coroutine:

______________________________________________________________________

# Threading and Processing

- __Description:__
- __Author:__ Kuan-Hsien Wu
- __Contact:__ jordankhwu@gmail.com
- __Date:__ 2023/07/09

## Terminology

### Atomic operation

- Indivisible operation

### Race condition

- If more than one operation change the same variable at the time, the variable will be read/written before it is read/written by other tasks

### Concurrency

- Multi-tasking ability
  - Context switching
    - Each task use the only core in assigned time and switch between each other
  - Parallelism
    - Each task is assigned to different core

### Synchronous

- Current task only processes after previous task finishes
  - Task runs sequentially
- For Synchronization,
  - Lock/Unlock is added to tasks to avoid race condition
  - Deadlock scenario occurs from locking order
    - Tasks are waiting each other to unlock themselves
    - In the end, nothing is unlocked

### Asynchronous

- Task processes without waiting other tasks to finish
  - Parallelism: Multi-threading
    - Suitable: heavy computation e.g. image processing
  - Concurrency: Asynchronous Programming
    - Suitable: lots of IOs e.g. web service

## Asynchronous Programming or Multi-threading

### Asynchronous Programming (multitasking on single-thread)

- Good for CPU-bound tasks (programs with a lot of I/O operations)
  - Since most of the threads are just waiting for I/O operations
  - e.g. read/write database, web scrapping

### Multi-threading

- Good for I/O-bound tasks (programs with a lot of computing operations)
  - e.g. decoding/encoding

## Multi-threading or Multi-processing

### Multi-threading

- Less stable since thread might be affected by other threads
- Race condition may occur

### Multi-processing

- More stable since process is not affected by other processes
- Cost more resources

## Process, Thread, Coroutine (Async) in Python

- A Process can contain N threads and a thread can contain N coroutines
  - Process: `multiprocessing`
    - Pros: Multiprocessing with multiple CPUs
    - Cons: Resource consuming, limited to CPU number
  - Thread: `threading`
    - Pros: Lighter than process
    - Cons:
      - Thread is synchronously running in python due to GIL
        - Global Interpreter Lock (GIL):
          - At one time, only one thread can be executed
          - GIL is released by thread in I/O period
      - Cost for context switching
  - Coroutine: `asyncio`
    - Pros: No number limit for coroutine, least resource consuming
    - Cons: Module supports, complex implementation

### GIL in python

# Reference

- https://www.youtube.com/watch?v=I3E4MHTpABA&list=WL&index=131
- https://www.youtube.com/watch?v=I3E4MHTpABA
- https://www.youtube.com/watch?v=6nCUP-E6nCU&list=PLCemT-oocganLyOGNbzH9YdaSbZEALXmJ
