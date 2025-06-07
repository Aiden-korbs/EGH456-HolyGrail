#### Summary:

The scheduler determines which task runs at any given time based on priority and system rules. FreeRTOS supports preemptive, time-sliced, and cooperative scheduling modes.

---

### ⚙️ Scheduler Algorithms

**Slide 2–5 Overview:**

- **Preemptive Scheduling**
    
    - Default in FreeRTOS
        
    - Highest-priority ready task always runs
        
- **Time Slicing**
    
    - Enabled if multiple tasks share top priority
        
    - Round-robin within equal priority group
        
    - Controlled by `configUSE_TIME_SLICING`
        
- **Cooperative Scheduling**
    
    - Tasks must yield explicitly using `taskYIELD()`
        
    - Simpler, but less responsive
        

**FreeRTOS Config Options:**

|Macro|Description|
|---|---|
|`configUSE_PREEMPTION`|Enables preemptive scheduler|
|`configUSE_TIME_SLICING`|Enables round-robin scheduling|

---

### 🔗 See Also

- [[Task States and Transitions]]
    
- [[Idle and Tick Hooks]]