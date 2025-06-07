#### Summary:

Interrupt latency is the delay between the triggering of an interrupt and the start of its handler. In real-time systems, low latency is critical for responsiveness.

---

### ⏱️ Interrupt Latency

**Slide 11–12 Overview:**

- Components of latency:
    
    - Time to complete current instruction
        
    - Time to push registers (context saving)
        
    - Time to fetch handler from vector table
        
- Affected by:
    
    - Critical section nesting (interrupts disabled)
        
    - Interrupt priority masking
        
    - Long ISR execution times
        

**Latency Reduction Techniques:**

- Minimize critical section length
    
- Use prioritized interrupts properly
    
- Defer long processing to tasks
    

---

### 🔗 See Also

- [[Critical Nesting]]
    
- [[Interrupt Priorities]]