
In FreeRTOS (and most RTOSs), deadlocks can occur if mutexes are requested in inconsistent orders.

**Example:**  
Two tasks, each try to take two mutexes, but in different orders.

```c
// Task1: Locks mutex1, then tries for mutex2
void Task1(void *param) {
    while(1) {
        xSemaphoreTake(mutex1, portMAX_DELAY);
        vTaskDelay(10); // Simulate time gap
        xSemaphoreTake(mutex2, portMAX_DELAY);
        // Critical section
        vTaskDelay(10);
        xSemaphoreGive(mutex2);
        xSemaphoreGive(mutex1);
        vTaskDelay(100); // Pause before retry
    }
}

// Task2: Locks mutex2, then tries for mutex1
void Task2(void *param) {
    while(1) {
        xSemaphoreTake(mutex2, portMAX_DELAY);
        vTaskDelay(10); // Simulate time gap
        xSemaphoreTake(mutex1, portMAX_DELAY);
        // Critical section
        vTaskDelay(10);
        xSemaphoreGive(mutex1);
        xSemaphoreGive(mutex2);
        vTaskDelay(100); // Pause before retry
    }
}
```
**Result:**

- If Task1 takes mutex1 and Task2 takes mutex2 at the same time, each waits forever for the other mutex.
    
- Neither can finish: the system is deadlocked.

**This can happen in any RTOS if locks/resources are acquired in different orders by different tasks.**