# Real-time Scheduling of Periodic Tasks

## What are Periodic Tasks?

Periodic tasks are tasks that must execute at fixed, regular intervals (their **period**).  
These are extremely common in embedded and real-time systems—for example, polling sensors, running control loops, or transmitting data at set intervals.

---

## Key Parameters

| Parameter              | Meaning                                   | Example |
| ---------------------- | ----------------------------------------- | ------- |
| **Period (T)**         | Time between each activation (release)    | 20 ms   |
| **Execution Time (C)** | CPU time required per activation          | 5 ms    |
| **Deadline (D)**       | Time by which each activation must finish | 20 ms   |

- *Usually, Deadline = Period in simple hard real-time systems.*

---

## Timeline Example

| Time (ms) | 0  | 10 | 20 | 30 | 40 | 50 | ... |
|-----------|----|----|----|----|----|----|-----|
| Task A    |[==]|    |[==]|    |[==]|    | ... |
|           |<-------- Period -------->|

- `[==]` = Task execution window (Exec Time)
- Each `[==]` starts at the period, must finish before next period (the deadline)

---

## How are Periodic Tasks Scheduled?

- The scheduler or RTOS ensures each periodic task starts at its correct interval.
- At every tick (e.g., every 10ms), the system checks which tasks are ready based on their periods.
- The task must complete its execution before its deadline (often the next release time).

---

## Simplifying Assumptions

- Tasks are independent (no blocking or resource contention).
- Execution time is known and worst-case.
- ISRs (interrupt service routines) do not interfere with periodic task scheduling.

---

## Practical Use Cases

- **Sensor polling:** Reading temperature, light, or pressure sensors every fixed interval.
- **Control loops:** Updating a PID control value every 5 or 10 ms.
- **Periodic communications:** Sending regular status updates or “heartbeat” messages.
- **Data logging:** Writing samples to memory or SD card at a defined rate.

---

## Why is this important?

- **Missing a deadline** can mean data loss, unstable control, or even safety hazards in critical systems.
- **Schedulability analysis** (e.g., Rate Monotonic Scheduling) helps engineers prove that all deadlines will be met under worst-case timing.

---

