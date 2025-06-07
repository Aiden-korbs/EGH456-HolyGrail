#### Summary:

Threads (called tasks in FreeRTOS) are the main unit of execution. Each task has its own stack, priority, and lifecycle. FreeRTOS manages task creation, scheduling, and transitions between states.

---

### 📦 Threads and Tasks

**Slide 7, 28–29, 34–37 Overview:**

- **Task Properties:**
    
    - Independent execution unit
        
    - Own scope, context, and stack
        
    - Waits for events or resource availability
        
- **Idle Task:**
    
    - Always runs when no other tasks are ready
        
    - Good for low-priority housekeeping
        
- **States:**
    
    - Ready: Eligible to run
        
    - Running: Currently executing
        
    - Blocked: Waiting (e.g., on delay or resource)
        
    - Suspended: Inactive until resumed
        

**Example Code:**

```c
void vTaskCode(void *pvParameters) {
  for (;;) {
    // main loop
  }
}

xTaskCreate(vTaskCode, "Task1", 1000, NULL, 1, NULL);
```

**Diagram Reference:** Slide 35–37

---

### 🔗 See Also

- [[RTOS Basics]]
    
- [[Synchronization]]