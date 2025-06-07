#### Summary:

FreeRTOS provides two user-definable hook functions: the Idle Hook and the Tick Hook. These allow executing background or periodic code without disrupting task scheduling.

---

### 🪝 Idle and Tick Hooks

**Slide 11–13 Overview:**

- **Idle Hook (`vApplicationIdleHook`)**
    
    - Called when no other tasks are ready
        
    - Can enter low-power mode or run background cleanup
        
    - Must not block!
        
- **Tick Hook (`vApplicationTickHook`)**
    
    - Called every tick interrupt (based on `configTICK_RATE_HZ`)
        
    - Useful for periodic updates or system timing
        
    - Must be short and fast
        

**Config Macros:**

|Macro|Purpose|
|---|---|
|`configUSE_IDLE_HOOK`|Enables Idle Hook|
|`configUSE_TICK_HOOK`|Enables Tick Hook|

---

### 🔗 See Also

- [[Scheduler Algorithms]]
    
- [[Task States and Transitions]]