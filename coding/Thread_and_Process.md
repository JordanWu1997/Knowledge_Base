# Threading and Processing
- https://www.youtube.com/watch?v=I3E4MHTpABA

Atomic operation
- Indivisible operation

Race condition
- If more than one operation change the same variable at the time, the variable will be read/written before it is read/written by other tasks

Concurrency
- Multi-tasking ability
    - Context switching
        - Each task use the only core in assigned time and switch between each other
    - Parallelism
        - Each task is assigned to different core

Synchronous
- Next task only processes after previous task finishes
- For Synchronization,
    - Lock/Unlock is added to tasks
    - Deadlock scenario occurs from locking order
        - Tasks are waiting each other to unlock themself, in the end, nothing is unlocked
Asynchronous
- Task processes without waiting other tasks to finish
    - Parallelism: Multi-threading
        - Suitable: heavy computation e.g. image processing
    - Concurrency: Asynchronous Programming
        - Suitable: lots of IOs e.g. web service

Multi-threading
- Less stable since thread might be affected by other threads
- Race condition may occur

Multi-processing
- More stable since process is not affected by other processes
- Cost more resources
