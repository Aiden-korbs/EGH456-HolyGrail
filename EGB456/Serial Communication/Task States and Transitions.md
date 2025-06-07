#### Summary:

Tasks in FreeRTOS move between well-defined states: Running, Ready, Blocked, Suspended, and Deleted. Understanding transitions between them is key to effective task control.

---

### 🔄 Task States and Transitions

**Slide 6–10 Overview:**

- **Running**: Currently executing on CPU
    
- **Ready**: Can run, waiting for CPU
    
- **Blocked**: Waiting for delay, semaphore, etc.
    
- **Suspended**: Inactive until explicitly resumed
    
- **Deleted**: Removed from scheduling (memory freed)
    

**Common Transitions:**

- Ready → Running: when scheduled
    
- Running → Blocked: calls delay or waits
    
- Running → Suspended: via `vTaskSuspend()`
    
- Running → Deleted: via `vTaskDelete()`
    

**Diagram Reference:** Slide 7

---

### 🔗 See Also

- [[Scheduler Algorithms]]
    
- [[Idle and Tick Hooks]]