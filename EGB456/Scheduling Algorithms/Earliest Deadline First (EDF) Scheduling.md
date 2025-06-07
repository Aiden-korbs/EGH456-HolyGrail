
## What is EDF?

- A dynamic-priority algorithm: The task with the closest (earliest) deadline always has the highest priority.
- Priorities are recalculated every scheduling event (task release, completion, etc.).

## Key Features

- **Dynamic priorities:** Each task’s urgency changes as its deadline approaches.
- **Maximum CPU utilization:** In theory, can schedule tasks up to 100% CPU usage (no static bound as with RMS).

## How It Works

- When a scheduling decision is needed, the scheduler picks the task whose deadline is nearest in the future.
- Every time a task is released or finishes, priorities are updated.

## Practical Considerations

- Implementation is more complex than RMS.
- In FreeRTOS, requires regular calls to set priorities dynamically (e.g., `vTaskPrioritySet()` every period).

## Drawbacks

- **Overload/cascading failure:** If the system is briefly overloaded, the earliest deadline task monopolizes the CPU, causing a domino effect where many deadlines are missed in sequence.
- Less robust than RMS in overload or blocking situations.

## Use Cases

- Soft real-time systems, multimedia processing, or where CPU utilization must be maximized and tasks have varied deadlines.

---
