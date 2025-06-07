
[[Concurrent Access Model]]  

## What is Mutual Exclusion?

- **MUTEX** (MUTual EXclusion): Ensures only one thread accesses a critical section/resource at a time.
    
- Required to avoid race conditions and data corruption.

## Protection Mechanisms

- Disable preemption/interrupts (vTaskSuspendAll, taskENTER_CRITICAL)
    
- Use a MUTEX (lock/unlock protocol)
    
- Use same-priority tasks
    

## Diagram Example

![](https://chatgpt.com/c/mutex_protection.png)

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
[[FreeRTOS Mutexes]]