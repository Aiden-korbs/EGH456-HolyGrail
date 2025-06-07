
[[Concurrent Access Model]] [[Critical Resource Protection - Mutual Exclusion]] [[Semaphore vs Mutex]] [[Priority Inversion]] [[Priority Inheritance]]

## Summary Table

|Region|Protection Mechanism|
|---|---|
|ISR/Task Shared|Disable interrupts (taskENTER_CRITICAL)|
|Task/Task Shared|Mutex, vTaskSuspendAll, taskENTER_CRITICAL|
|Task/ISR Shared|Disable interrupts (taskENTER_CRITICAL_FROM_ISR)|

- Use **mutexes** for task-to-task resource protection.
    
- Disable interrupts for ISR interactions.
    