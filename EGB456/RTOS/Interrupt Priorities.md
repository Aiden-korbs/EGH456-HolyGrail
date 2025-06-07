#### Summary:

Interrupt priority levels determine the urgency of servicing various interrupt sources. Cortex-M MCUs use a nested vector interrupt controller (NVIC) with configurable priority levels.

---

### ⚡ Interrupt Priorities

**Slide 4–6 Overview:**

- NVIC supports multiple priority levels (e.g. 0–255 on ARM Cortex-M4F)
    
- Lower numerical value = higher priority (e.g. 0 is highest)
    
- `configMAX_SYSCALL_INTERRUPT_PRIORITY` defines the highest interrupt level from which RTOS calls are safe
    
- Priorities are grouped and sub-grouped using bits (e.g. 3-bit pre-emption)
    

**Interrupt pre-emption rules:**

- Higher-priority interrupts preempt lower-priority ones
    
- Same-priority interrupts do not preempt each other
    

**Diagram Reference:** Slide 6

---

### 🔗 See Also

- [[Critical Nesting]]
    
- [[Interrupt Latency]]