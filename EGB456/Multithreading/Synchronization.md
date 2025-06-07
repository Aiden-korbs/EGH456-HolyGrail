#### Summary:

Synchronization mechanisms such as semaphores and mutexes help manage concurrent access to resources and coordinate task execution in FreeRTOS.

---

### 🧰 Synchronization

**Slide 47–52 Overview:**

- **Semaphores:**
    
    - Binary: 0 or 1, used for signaling or exclusive access
        
    - Counting: allow N concurrent accesses (like ticketing)
        

**Analogy:**

- Library: 5 books, first 5 people borrow one; 6th waits or returns later
    

---

### ⚙️ API Summary

|Function|Purpose|
|---|---|
|`xSemaphoreGive()`|Release from task|
|`xSemaphoreTake()`|Acquire in task|
|`xSemaphoreGiveFromISR()`|Release from ISR|
|`xSemaphoreTake(..., portMAX_DELAY)`|Block indefinitely until available|

---

### 🔗 See Also

- [[ISR Design]]
    
- [[Shared Resources]]