
[[Critical Resource Protection - Mutual Exclusion]]  

|Feature|Mutex|Binary Semaphore|
|---|---|---|
|Priority Inheritance|Yes|No|
|ISR Safe?|No|Yes|
|Usage|Mutual Exclusion|Synchronization|
|Blocking Timeout|Yes|Yes|

## Explanation

- **Mutex:** Locking mechanism; ownership tracked; only owner can unlock.
    
- **Semaphore:** Signaling mechanism; any thread can give/take.
    

## FreeRTOS

- Mutexes in FreeRTOS are binary semaphores with _priority inheritance_ for real-time safety.
    
- Mutexes only work between tasks (not ISRs).
    

![](https://chatgpt.com/c/mutex_vs_semaphore.png)

[[Priority Inversion]]