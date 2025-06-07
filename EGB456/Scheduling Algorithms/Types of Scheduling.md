
## 1. Co-operative (Non-preemptive) Scheduling

- Each task runs until it voluntarily yields, blocks, or finishes.
- Even if a higher-priority task is ready, it must wait for the running task to release the CPU.
- **Pros:** Simple, low overhead, easy to understand.
- **Cons:** Poorly-written tasks can block others, not suitable for most real-time needs.

## 2. Pre-emptive Scheduling

- The scheduler can pause the currently running task at any time to run a higher-priority one.
- Equal-priority tasks can be alternated using time slicing (unless disabled).
- **Pros:** Ensures urgent tasks run as soon as they are ready. More predictable for hard real-time deadlines.
- **Cons:** More complex, risk of race conditions if not careful with resource sharing.

## 3. Time Slicing

- Special case of preemptive scheduling for tasks with the same priority.
- The scheduler assigns each equal-priority task a fixed time slice, cycling through them in a round-robin manner.
- **Use Case:** Fairness for background or periodic tasks, e.g., UI updates, sensor polling.

---
