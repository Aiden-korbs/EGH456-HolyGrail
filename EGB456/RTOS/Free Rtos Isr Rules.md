#### Summary:

FreeRTOS has strict rules for what functions can be called from an ISR. Using the correct `FromISR()` variants is essential for system stability.

---

### 📏 FreeRTOS ISR Rules

**Slide 16 Overview:**

- **Only use `FromISR()` APIs in ISRs:**
    
    - `xSemaphoreGiveFromISR()`
        
    - `xQueueSendFromISR()`
        
    - `xTaskNotifyFromISR()`
        
    - Always pass `pxHigherPriorityTaskWoken`
        

**Why it matters:**

- Regular FreeRTOS APIs can corrupt system state if used from an ISR
    
- Scheduler decisions are deferred until `portYIELD_FROM_ISR()` is called if necessary
    

**Example:**

```c
void ISR_Handler(void) {
  BaseType_t xHigherPriorityTaskWoken = pdFALSE;
  xQueueSendFromISR(queue, &data, &xHigherPriorityTaskWoken);
  portYIELD_FROM_ISR(xHigherPriorityTaskWoken);
}
```

---

### 🔗 See Also

- [[ISR Design]]
    
- [[Interrupt Masking]]