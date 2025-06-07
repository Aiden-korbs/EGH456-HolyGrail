## What is Time Slicing?

- Time slicing lets tasks of the same priority share CPU in a round-robin fashion.
- The scheduler gives each ready task a fixed time slice (quantum) to run, then moves to the next.

## How It Works

- On each system tick (timer interrupt), the scheduler checks if the running task’s time slice is up.
- If so, the next equal-priority task is selected to run.
- Cycle repeats, ensuring all equal-priority tasks get a fair share.

## Properties

- **Fairness:** All tasks of equal priority get CPU time.
- **Interruptibility:** Higher-priority interrupts/tasks can still preempt at any time.
- **Efficiency:** Prevents any one background task from monopolizing the CPU.

## Example

- Three sensor polling tasks at equal priority, each runs for 10ms in turn.
- If an urgent event occurs, a higher-priority task can still preempt immediately.

---
