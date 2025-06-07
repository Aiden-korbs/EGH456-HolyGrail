
## Beyond Single-core Scheduling
- Many embedded systems now use **multi-core (SMP)** processors. Traditional uni-processor scheduling algorithms may not suffice for these platforms.
- **Task affinity:** In SMP systems, some RTOSs allow you to "pin" tasks to specific cores for cache efficiency or timing reasons, or let the kernel pick the N highest-priority ready tasks to distribute among cores.

## Distributed Systems
- Some embedded/real-time systems are distributed—tasks run on different chips, boards, or even over networks (cloud robotics, IoT).
- Message passing between nodes introduces communication delays and synchronization overhead.

## Resource Sharing Impact
- Tasks that share resources (data, peripherals) must synchronize access, which can introduce waiting (blocking) and impact timing guarantees.
- Priority inversion or deadlock are risks if not managed properly (see previous lectures).

## Research & Solutions
- Many advanced scheduling models and protocols have been developed to handle SMP, resource sharing, and distributed real-time requirements.
- Always analyze the effect of shared resources and communication delays in your system's timing analysis.
