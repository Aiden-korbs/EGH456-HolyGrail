#### Summary:

Interrupt Service Routines (ISRs) handle real-time hardware events. In RTOS-based systems, ISRs must be minimal and defer processing to tasks to avoid blocking and ensure system responsiveness.

---

### 🚨 ISR Design

**Slide 27, 40–44 Overview:**

- **Best Practices:**
    
    - Short and fast
        
    - Use `FromISR` API functions
        
    - Clear hardware flags promptly
        
    - Use semaphores or queues to signal tasks
        

**Example:**

```c
void ISR_Handler(void) {
  BaseType_t xHigherPriorityTaskWoken = pdFALSE;
  ClearInterruptFlag();
  xSemaphoreGiveFromISR(xSemaphore, &xHigherPriorityTaskWoken);
  portYIELD_FROM_ISR(xHigherPriorityTaskWoken);
}
```

**Follow-up Task:**

```c
void vTask(void *pvParams) {
  for (;;) {
    if (xSemaphoreTake(xSemaphore, portMAX_DELAY)) {
      // Process event
    }
  }
}
```

---

### 🔗 See Also

- [[Synchronization]]
    
- [[Context Switching]]