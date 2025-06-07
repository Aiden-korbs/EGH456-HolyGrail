#### Summary:

Trace hook macros in FreeRTOS allow developers to insert application-specific instrumentation at key RTOS events such as task switching or queue operations.

---

### 🧪 Trace Hook Macros

**Slide 14–15 Overview:**

- Defined in `FreeRTOSConfig.h`
    
- Used to profile task execution, log switching, and monitor RTOS activity
    
- Hook points include:
    
    - `traceTASK_SWITCHED_IN`
        
    - `traceTASK_SWITCHED_OUT`
        
    - `traceTASK_CREATE`
        
    - `traceTASK_DELETE`
        

**Example:**

```c
#define traceTASK_SWITCHED_IN() myTraceLog(pcTaskGetName(NULL))
```

**Config Flags:**

|Macro|Description|
|---|---|
|`configUSE_TRACE_FACILITY`|Enables trace hooks globally|
|`INCLUDE_xTaskGetCurrentTaskHandle`|Needed for introspection|

**Use Cases:**

- Debugging and profiling
    
- Runtime statistics generation
    

---

### 🔗 See Also

- [[Idle and Tick Hooks]]
    
- [[Scheduler Algorithms]]