
## How to Prevent or Handle Deadlock

### 1. Prevention through Design

- **Resource ordering:**  
  Always acquire multiple resources in a global, agreed order (e.g., always lock mutexA before mutexB everywhere in your code). This eliminates the possibility of circular wait.
- **No hold-and-wait:**  
  Require that a task requests *all* needed resources at once, and releases them all before requesting more. This is often impractical for complex systems but is effective for simple ones.
- **Enable preemption:**  
  Allow resources to be forcibly taken back (rare in RTOSes, but possible with timeouts or cancellation).

### 2. Timeouts and Watchdogs

- Use timeouts when acquiring resources: If a resource isn’t available after a set time, abort, retry, or roll back.
- Use a watchdog/supervisory task to detect and recover from stuck threads (restart or signal them).

### 3. Deadlock Detection and Recovery

- Use tools or OS support (e.g., wait-for graphs) to detect cycles in resource allocation.
- Recovery may involve killing or restarting blocked tasks, or forcibly reclaiming resources.

## Best Practice

- Most embedded systems prevent deadlock by **imposing a strict locking order** and using timeouts or non-blocking attempts when possible.

---

### Livelock.md

```markdown
# Livelock

## What is Livelock?

- **Livelock** is when two or more tasks continuously change state in response to each other, but no useful progress is made.
- Unlike deadlock, tasks are not blocked—they remain active but “dancing around the problem.”

### Example

- Two tasks keep releasing and re-acquiring a lock to be polite (e.g., see the other wants it), but both just keep retrying endlessly.
- Real-world analogy: Two people trying to pass each other in a hallway, both stepping aside for the other, but never moving forward.

## In Code

```c
while(1) {
    if (try_acquire_resource()) {
        // Do work
        break;
    } else {
        // If resource unavailable, immediately retry or yield
        taskYIELD(); // If both do this, neither may ever get the lock!
    }
}
```
**Result:**  
Both tasks keep retrying and yielding to each other, but nothing gets done.
