
[[Concurrent Access Model]]  
## What is Mutual Exclusion?

- **MUTEX** (MUTual Exclusion): Ensures only one thread accesses a critical section/resource at a time.
    
- Required to avoid race conditions and data corruption.

## Protection Mechanisms

- Disable preemption/interrupts (vTaskSuspendAll, taskENTER_CRITICAL)
    
- Use a MUTEX (lock/unlock protocol)
    
- Use same-priority tasks
    
## Code Example

```c
// Using FreeRTOS Mutex
SemaphoreHandle_t xMutexHandle;
xMutexHandle = xSemaphoreCreateMutex();
xSemaphoreGive(xMutexHandle);

// Critical Section
xSemaphoreTake(xMutexHandle, portMAX_DELAY);
// ...protected code...
xSemaphoreGive(xMutexHandle);
```

## See Also

[[Semaphore vs Mutex]]  