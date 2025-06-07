
## Overview

- In embedded systems, **concurrent access** refers to situations where multiple threads (tasks or ISRs) may try to access a shared resource at any time, with no enforced protocol.
    
- This can lead to **contention** (conflicts), pre-emption, and timing problems.
    

## Key Points

- _Any_ thread can access the resource at _any_ time.
    
- Without protection, pre-emption of one thread by another can cause contention.
    
- **Problems:** Priority inversion, deadlock.
    

## Example Diagram

![](https://chatgpt.com/c/concurrent_access_model.png)

## Last Lecture Reference

See [[Resource Sharing and Producer-Consumer Model]] for context.

## Solutions

- Disable interrupts/preemption (brute force)
    
- Use MUTEX mechanism
    
- Use same priority for all threads (not always possible)
    

[[Critical Resource Protection - Mutual Exclusion]]