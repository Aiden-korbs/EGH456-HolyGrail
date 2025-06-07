
## What is Preemptive Scheduling?

- **Preemptive scheduling** allows the RTOS to interrupt a running task at any time to immediately start a higher-priority task.
- Ensures that urgent tasks always get CPU time when needed, regardless of what else is running.

## How It Works

- A task switch occurs whenever a higher-priority task becomes ready (due to an interrupt, event, or data availability).
- The running task's state is saved, and the higher-priority task's state is restored.

## Response Time

- **Response time = interrupt latency + context switch latency**
  - *Interrupt latency*: Time to recognize/respond to the interrupt.
  - *Context switch latency*: Time to save the current task state and restore the next one.

## Example

- Task A (background) is running.
- An interrupt signals Task B (high priority) is ready.
- The RTOS switches to Task B immediately, minimizing response time for critical events.

## Pros & Cons

- **Pros:** Predictable, guarantees deadlines for high-priority tasks, prevents CPU hogging.
- **Cons:** More CPU overhead, requires robust handling of shared resources (risk of race conditions).

---
