#### Summary:

Interrupt masking allows selective disabling of interrupts to manage execution order and protect critical sections in Cortex-M processors.

---

### 🛡️ Interrupt Masking

**Slide 14–15 Overview:**

- **PRIMASK**
    
    - 1-bit register
        
    - Masks all exceptions except NMI and HardFault
        
    - Useful for quick critical sections
        
- **FAULTMASK**
    
    - Masks all exceptions except NMI
        
    - Used in fault handlers
        
- **BASEPRI**
    
    - Masks interrupts with priorities numerically ≥ BASEPRI
        
    - Allows selective masking
        
    - Requires careful bit-shift configuration (priority << (8 - __NVIC_PRIO_BITS))
        

**Register Access (CMSIS):**

```c
__disable_irq(); // PRIMASK = 1
__enable_irq();  // PRIMASK = 0

__set_BASEPRI(priority); // mask lower-priority interrupts
__get_BASEPRI();
```

**Diagram Reference:** Slide 15

---

### 🔗 See Also

- [[Critical Nesting]]
    
- [[FreeRTOS ISR Rules]]