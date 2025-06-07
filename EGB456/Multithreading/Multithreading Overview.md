#### Summary:

This topic introduces key multithreading models used in embedded systems. It compares polling, ISR-driven, and RTOS-based scheduling approaches. RTOS-based multithreading enables responsiveness, modularity, and scalable task management.

---

### 🧵 Threading Models

**Slide 4–6 Overview:**

#### 1. Single Thread Polling

- Main loop checks each device sequentially
    
- Simple but blocking delays reduce responsiveness
    

#### 2. Single Thread + ISRs

- Interrupts handle asynchronous events
    
- Blocking or long ISRs can cause missed deadlines
    

#### 3. Multithreaded with RTOS

- ISRs queue data; tasks process data
    
- Enhances responsiveness and modularity
    
- Short ISRs, deferred processing, software-prioritized threads
    

**Diagram Reference:** Slide 6

---

### 🔗 See Also

- [[Context Switching]]
    
- [[Threads and Tasks]]
    
- [[EGB456]]