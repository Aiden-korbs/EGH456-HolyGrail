
|                    | Deadlock                      | Livelock                            |
|--------------------|-------------------------------|-------------------------------------|
| Progress stopped?  | Yes (nothing proceeds)        | No, but no useful work is done      |
| Threads blocked?   | Yes (each waits forever)      | No (always running/yielding)        |
| Solution           | Break the 4 conditions, detect/recover | Add backoff, redesign retry logic  |

- **Deadlock:** System halts; everyone waits forever.
- **Livelock:** System “spins its wheels;” tasks keep running but never succeed.

---

### Reference Patterns and Best Practices.md

```markdown
# Reference Patterns and Best Practices

- **Document all resource acquisition orderings:**  
  Make clear in your codebase and design docs how and in what order locks/resources are acquired.
- **Use RTOS-provided mutexes/semaphores:**  
  These are typically tested and robust, reducing risk of bugs in home-grown locking code.
- **Prefer timeouts for blocking calls:**  
  Never block forever on a resource unless you are absolutely sure there’s no risk of deadlock.
- **Test under stress and fault conditions:**  
  Use simulated faults, high-load scenarios, or chaos testing to provoke rare deadlock/livelock events.
- **Employ watchdogs or supervisor tasks:**  
  These can monitor thread progress and take action if a task is stuck for too long.

