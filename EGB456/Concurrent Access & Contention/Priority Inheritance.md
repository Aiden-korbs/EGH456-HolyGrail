
[[Priority Inversion]]  
[[Semaphore vs Mutex]]  

## What is Priority Inheritance?

- Protocol where the _lower-priority task_ holding a resource temporarily inherits the _higher_ priority of any waiting task.
    

## Implementation in FreeRTOS

- FreeRTOS mutexes use priority inheritance by default.
    
- Prevents excessive blocking of high-priority tasks by low-priority tasks.
    

## Code Example (FreeRTOS Mutex)

```c
SemaphoreHandle_t xMutex = xSemaphoreCreateMutex();
if(xSemaphoreTake(xMutex, portMAX_DELAY)) {
    // Critical Section
    xSemaphoreGive(xMutex);
}
```

## Limitations

- Does NOT prevent deadlock.
    
- Priority ceiling protocol is an alternative for deadlock prevention (not covered in detail here).
    

![](https://chatgpt.com/c/priority_inheritance_example.png)

[[Mars Pathfinder Case - 1997]]