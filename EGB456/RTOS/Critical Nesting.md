#### Summary:

Critical nesting allows multiple levels of critical sections without prematurely re-enabling interrupts. FreeRTOS tracks how many times interrupts have been disabled.

---

### 🧩 Critical Nesting

**Slide 7–10 Overview:**

- Uses `ulCriticalNesting` counter
    
- Each `taskENTER_CRITICAL()` increments counter
    
- Each `taskEXIT_CRITICAL()` decrements counter
    
- Interrupts re-enabled only when counter = 0
    

**Benefits:**

- Allows nested calls to critical sections safely
    
- Prevents race conditions during shared resource access
    

**Warning:**

- Failing to balance enter/exit calls causes interrupts to stay disabled indefinitely
    

**Diagram Reference:** Slide 10

---

### 🔗 See Also

- [[Interrupt Priorities]]
    
- [[Interrupt Latency]]