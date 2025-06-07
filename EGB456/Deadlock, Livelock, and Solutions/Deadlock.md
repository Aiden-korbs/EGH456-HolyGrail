
## What is Deadlock?

- **Deadlock** occurs in concurrent systems when two or more threads (or tasks/processes) each wait forever for a resource held by another, so none can proceed.
- All progress halts: the system appears frozen, but no thread can finish.
- Deadlocks can occur in OS kernels, embedded systems, databases, or any place with shared resources and multiple execution paths.

### Four Necessary Conditions for Deadlock

A deadlock can arise only if **all four** of these conditions hold:
1. **Mutual exclusion** — At least one resource can be held by only one thread at a time.
2. **Hold and wait** — Threads currently holding resources can request and wait for additional resources.
3. **No preemption** — Resources can’t be forcibly taken away; they’re released voluntarily.
4. **Circular wait** — A closed chain exists where each thread waits for a resource held by the next in the chain.

**If you break any one of these, deadlock is impossible.**

---

### Classic Deadlock Example

Suppose you have two resources (mutexes, files, peripherals) and two tasks:

- **Task A** locks resource 1, then tries to lock resource 2.
- **Task B** locks resource 2, then tries to lock resource 1.

If Task A and Task B both acquire their first resource, and then each tries to get the other, both are stuck—each is waiting on the other to release a lock.

**Pseudocode:**

```c
// Task A
take(res_1);        // Locks resource 1
take(res_2);        // Blocks here if B holds res_2
// Use both resources
give(res_2);
give(res_1);

// Task B
take(res_2);        // Locks resource 2
take(res_1);        // Blocks here if A holds res_1
// Use both resources
give(res_1);
give(res_2);
