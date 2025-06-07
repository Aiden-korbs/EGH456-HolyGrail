#### Summary:

The Nested Vectored Interrupt Controller (NVIC) in Cortex-M processors allows configuration of interrupt priority and grouping to balance responsiveness and control.

---

### 🧠 NVIC Configuration

**Slide 5, 6 Overview:**

- Priorities encoded using 8-bit fields
    
- Only upper bits implemented (e.g., 3 bits for STM32 = 8 priority levels)
    
- Bit shifting used:
    
    ```c
    NVIC_SetPriority(TIM2_IRQn, 5 << (8 - __NVIC_PRIO_BITS));
    ```
    
- Grouping = Preemption vs Subpriority:
    
    - `NVIC_PriorityGroup_4`: All bits for preemption
        
    - `NVIC_PriorityGroup_0`: All bits for subpriority
        

**Priority Register Layout:**

- Higher bits = more global interrupt control
    
- Lower bits = finer-grained, non-preemptive sequencing
    

**Diagram Reference:** Slide 6

---

### 🔗 See Also

- [[Interrupt Priorities]]
    
- [[Interrupt Masking]]