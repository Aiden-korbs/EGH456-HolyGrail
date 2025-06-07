#### Summary:

Context switching allows an RTOS to pause one thread and resume another by saving and restoring CPU state. It enables concurrent execution of multiple threads with isolated states.

---

### 🔁 Context Switching

**Slide 34–35 Overview:**

- **Context** = Complete CPU state (registers, stack pointer, program counter)
    
- **Switching**:
    
    - Save current context (Thread A)
        
    - Load new context (Thread B)
        
    - Controlled by RTOS scheduler or triggered by ISR
        

---

### 💾 What’s Stored in a Context

- General purpose registers (R0–R12)
    
- Program Counter (PC)
    
- Stack Pointer (SP)
    
- Link Register (LR)
    
- Program Status Register (PSR)
    

**Diagram Reference:**

- Slide 34–35: Diagram showing register sets and thread stack frames
    

---

### ⚙️ How Context Switch Occurs

|Step|Description|
|---|---|
|1|Triggered by timer ISR or API call|
|2|Save Thread A context to its stack|
|3|Scheduler selects Thread B|
|4|Restore Thread B context from its stack|
|5|Resume execution from saved PC|

---

### 🔍 Key Points

- Time-sliced or priority-based switching
    
- Enables multitasking on a single CPU
    
- Needs to be efficient to avoid excessive overhead
    

---

### 🔗 See Also

- [[EGB456/Build Process/Multithreading Overview]]]
    
- [[Critical Sections]]
[[Build Process]]