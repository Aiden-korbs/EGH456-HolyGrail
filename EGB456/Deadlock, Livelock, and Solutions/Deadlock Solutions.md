
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
