#### Summary:

Multithreading in embedded systems allows multiple tasks to run concurrently or switch context, improving responsiveness and modularity. ISRs handle hardware-level events, while threads perform background processing.

---

### 🧵 Multithreading Overview

**Slide 27–31 Overview:**

- **Threads**: Independent flows of execution managed by an RTOS
    
- **ISR (Interrupt Service Routine)**: Fast handler triggered by hardware events
    
- **Context Switching**: Mechanism to swap between threads based on priority or time
    

---

### 🧰 Programming Models

1. **Single Thread Polling** (Slide 28)
    
    - Main loop polls each device sequentially
        
    - Simple but inefficient
        
    - Blocking calls cause delays
        
2. **Single Thread + ISR** (Slide 29)
    
    - Initialization followed by wait-for-interrupt loop
        
    - ISRs handle hardware directly
        
    - Risk of ISR overrun or excessive blocking
        
3. **Multithreaded with Queued ISRs** (Slide 30–31)
    
    - ISRs push data into queues quickly, then return
        
    - Background threads process queued data
        
    - Efficient and responsive design
        

**Diagram Reference:**

- Slide 30: Thread queue and ISR decoupling
    

---

### ✅ Benefits of Multithreading

- Modular design: easier to write/debug individual threads
    
- Real-time performance: quick ISR response
    
- Simplified ISR: just push data to queue, no logic inside
    
- Optimized for latency: background threads handle bulk processing
    

---

### 🔗 See Also

- [[Context Switching]]
    
- [[Critical Sections]]