## What is a Scheduler?

- The **scheduler** is the decision-making component of the RTOS that determines which task or thread should run at any given time.
- It continuously evaluates:
  - The state of all tasks (ready, running, blocked, sleeping)
  - System rules and priorities
  - Upcoming deadlines or time slices

## How Does it Decide?
- Based on a chosen **scheduling algorithm** (see below), considering priority, deadlines, and task readiness.
- Runs on key system events: after interrupts, at every system tick, or when tasks yield/block/finish.

## Core Role
- Keeps the system responsive and predictable.
- Ensures that the highest-priority or most urgent task is always running when possible.
- Guarantees time-sensitive operations meet their deadlines.

## Example in Action
- If an ISR signals that new data is available, the scheduler may immediately switch from a background logging task to a data
