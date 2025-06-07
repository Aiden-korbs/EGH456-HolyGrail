#### Summary:

Shared resources like global variables or peripherals must be protected in concurrent systems. Accessing them unsafely can lead to race conditions, data corruption, or inconsistent behavior.

---

### 🧩 Shared Resources

**Slide 11–12, 15 Overview:**

- Common shared elements:
    
    - Global variables (e.g., `count`)
        
    - Buffers
        
    - UART / GPIO
        
- Risks:
    
    - Race conditions
        
    - Data overwritten by preempted tasks
        

**Example Problem:**

```c
// Task A
count += 1;  // Not atomic!

// Task B
count = 0;
count += 1;
```

---

### 🛡️ Protection Techniques

|Method|Description|
|---|---|
|Disable Scheduler|Prevents task switching, not ISRs|
|Disable Interrupts|Safe for very short critical sections|
|Mutex/Semaphore|Best for RTOS-based synchronization|

---

### 🔗 See Also

- [[Synchronization]]
    
- [[Context Switching]]