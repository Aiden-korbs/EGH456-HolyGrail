
## What is a Completion Deadline?

- The absolute latest time by which a task (or ISR) must finish to maintain system correctness and safety.
- Missing a deadline can mean system instability, data loss, or even physical danger.

## Task vs ISR Deadlines

- **ISRs (Interrupt Service Routines):**
  - Designed for ultra-fast, critical event handling (microsecond or less response).
  - Should finish quickly; main work is deferred to a task if possible.
- **Tasks:**
  - Perform more extensive work (data processing, control, communication).
  - Must be scheduled to finish within their assigned deadline for system correctness.

## Example

- A control loop running every 10ms must finish before the next cycle starts.
- An overcurrent ISR on a motor driver must react in microseconds to prevent hardware damage.

## Importance

- Hard deadlines (must never be missed): e.g., safety-critical controls.
- Soft deadlines (rare misses tolerated): e.g., periodic data logging.

---
