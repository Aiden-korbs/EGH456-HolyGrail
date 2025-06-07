

## Common Real-time Scheduling Algorithms

### Rate Monotonic Scheduling (RMS)
- Assigns static priorities: tasks with shorter periods get higher priority.
- Simple, efficient, predictable; ideal for periodic tasks with constant rates.

### Earliest Deadline First (EDF)
- Assigns dynamic priorities: the task with the nearest deadline always runs next.
- Supports higher CPU utilization (up to 100% in theory), but is more complex.

### Stu Monotonic
- All tasks start at equal priority. If a task misses its deadline, its priority is temporarily increased.

### Round Robin
- Equal-priority tasks share CPU in turn, each with a fixed time slice.

### Others
- **Minimum Laxity:** Chooses the task with the least “slack” time before its deadline.
- **Deadline Monotonic:** Static-priority; shorter deadline gets higher priority.

## Selection Factors

- Task characteristics (periodic, aperiodic)
- Hard vs soft real-time needs
- Resource sharing and blocking potential

---
