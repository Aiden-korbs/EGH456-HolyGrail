#### Summary:

Critical sections are parts of code that access shared resources and must not be interrupted. Protecting critical sections prevents race conditions, data corruption, and inconsistent behavior.

---

### 🔐 Critical Sections

**Slide 36–37 Overview:**

- A **critical section** is any piece of code that modifies shared resources:
    
    - Buffers
        
    - UART
        
    - Global variables
        
    - Peripheral registers
        
- **Race Condition**: Occurs when two threads access a shared resource without coordination, leading to unpredictable results.
    

---

### 🧱 Common Shared Resources

- Output buffers (e.g., for `printf`)
    
- Communication interfaces
    
- Non-reentrant functions
    

**Example Problem (Slide 37):**

```c
// Thread A
printf("HELLO\n");

// Thread B
printf("goodbye");

// Possible corrupted output:
// HgoELodLO\nbye
```

---

### 🛡️ Protection Mechanisms

|Method|Description|
|---|---|
|Disabling interrupts|Temporarily prevents ISR context switches|
|Mutexes / Semaphores|Blocks access by other threads|
|Spinlocks (rare in RTOS)|Busy wait until resource is free|
|Scheduler lock (RTOS API)|Prevents context switching for a short time|

---

### ⚠️ Tips

- Keep critical sections short
    
- Avoid `printf` or blocking operations inside critical sections
    
- Protect every access to shared resource—not just writes
    

---

### 🔗 See Also

- [[Context Switching]]
    
- [[EGB456/Build Process/Multithreading Overview]]