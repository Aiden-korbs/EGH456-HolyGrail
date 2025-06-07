
## How to Prevent or Fix Livelock

- **Random backoff:**  
  Insert random delays between retries, so eventually one task will acquire the resource while the other waits.
- **Bounded retries:**  
  After a set number of failed attempts, escalate (e.g., notify a supervisor task, back off longer, or log a warning).
- **Protocol redesign:**  
  Use a lock protocol that guarantees eventual progress (e.g., use priorities or queuing).

**Example with random backoff:**

```c
while(1) {
    if (try_acquire_resource()) {
        // Success
        break;
    } else {
        vTaskDelay(rand() % 10); // Wait a random time before retry
    }
}
```
- The randomness ensures that not all tasks retry at the same instant, so progress can occur.