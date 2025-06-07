#### Summary:

A Real-Time Operating System (RTOS) manages multiple threads (tasks), scheduling them based on priority and system events. FreeRTOS is a lightweight RTOS designed for embedded systems.

---

### ⚙️ RTOS Basics

**Slide 22–26, 45–46 Overview:**

- **RTOS Services:**
    
    - Task creation and prioritization
        
    - Interrupt integration
        
    - Semaphores, queues, and synchronization
        
    - Tick-based timekeeping
        
- **FreeRTOS Features:**
    
    - Preemptive or cooperative scheduling
        
    - Small footprint, fast context switching
        
    - Modular and portable across MCU platforms
        

**Configuration (FreeRTOSConfig.h):**

|Macro|Purpose|
|---|---|
|configUSE_PREEMPTION|Enable preemptive scheduling|
|configTICK_RATE_HZ|System tick frequency|
|configMINIMAL_STACK_SIZE|Task stack size|
|configMAX_PRIORITIES|Max task priority levels|
|configUSE_MUTEXES|Enable mutex support|

---

### 🔗 See Also

- [[Threads and Tasks]]
    
- [[Synchronization]]