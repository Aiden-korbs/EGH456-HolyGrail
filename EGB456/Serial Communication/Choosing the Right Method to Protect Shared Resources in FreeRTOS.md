# Choosing the Right Method to Protect Shared Resources in FreeRTOS

| Access Scenario                | Recommended Method                       | Notes                                                  |
|------------------------------- |-----------------------------------------|--------------------------------------------------------|
| Task ↔ Task                    | Semaphore or Mutex                      | Use `xSemaphoreTake()` / `xSemaphoreGive()`            |
| Task ↔ Task (non-blocking)     | Critical Section (`taskENTER/EXIT_CRITICAL`) | Use for fast, non-blocking access (e.g., flags)   |
| ISR → Task (write, task reads) | Protect task side with Critical Section | ISR can't be interrupted by task, but task can by ISR  |
| Task → ISR (task writes, ISR reads) | Avoid or use `portSET_INTERRUPT_MASK_FROM_ISR()` | Difficult to get right, avoid if possible    |
| ISR signals event to task      | Semaphore or Queues                     | Use `xSemaphoreGiveFromISR()`, `vTaskNotifyGiveFromISR()`|