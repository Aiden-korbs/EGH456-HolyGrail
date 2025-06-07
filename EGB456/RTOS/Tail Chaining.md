#### Summary:

Tail chaining is an efficiency feature in Cortex-M processors where multiple interrupts can be handled back-to-back without full exception return and re-entry overhead.

---

### 🔄 Tail Chaining

**Slide 13 Overview:**

- When a higher-priority interrupt becomes pending during the exit of another interrupt handler, tail chaining skips:
    
    - Full context restore
        
    - Vector fetch delay
        
- Result: Faster ISR-to-ISR transition
    

**Benefits:**

- Lower latency
    
- Higher throughput for systems with high interrupt activity
    

**Example Scenario:**

- Interrupt A finishes, but before restoring context, Interrupt B becomes pending → directly switch to Interrupt B
    

**Diagram Reference:** Slide 13

---

### 🔗 See Also

- [[Interrupt Latency]]
    
- [[Interrupt Priorities]]