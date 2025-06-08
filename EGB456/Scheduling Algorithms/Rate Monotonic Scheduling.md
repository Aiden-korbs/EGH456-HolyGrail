
## What is RMS?

- A static-priority scheduling algorithm for periodic real-time tasks.
- **Policy:** The shorter a task's period (the more frequently it must run), the higher its priority.
- Priorities are assigned before runtime and never change.

## Assumptions

- Tasks are periodic, independent, and have constant execution times.
- Single CPU, no context switch overhead.
- Each deadline = end of its period.

## Schedulability Bound

- The maximum allowable CPU utilization for N tasks is:  
  `Bound = N*(2^(1/N) – 1)`
- 1 task: 100%  
  2 tasks: 83%  
  3 tasks: 78%  
  Many tasks: approaches 69%

- If total CPU usage < bound, all deadlines will always be met.

## Example

- Task A: Period = 20ms, Exec = 10ms
- Task B: Period = 50ms, Exec = 25ms
- Utilization = (10/20) + (25/50) = 1.0 (100%)  
  This is at the schedulable limit.

## Strengths & Limitations

- **Strengths:** Simple, predictable, works well for many real-time periodic systems.
- **Limitations:** Not suitable for aperiodic tasks or dynamically changing periods; resource sharing complicates things (priority inversion risk).

---
