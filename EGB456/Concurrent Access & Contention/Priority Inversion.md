
[[Semaphore vs Mutex]]  
## What is Priority Inversion?

- Occurs when a high-priority task is **blocked** by a lower-priority task holding a resource.
    
- The relative priorities of the tasks are effectively _inverted_.
    

## Example

- Low-priority Task acquires a lock.
    
- High-priority Task is blocked waiting for the lock.
    
- Medium-priority Task pre-empts and runs, causing unbounded delay.
    
## Types

- **Bounded**: Delay is limited to duration of low-priority task's critical section.
    
- **Unbounded**: Medium-priority task can run indefinitely, blocking high-priority.
    

[[Priority Inheritance]]