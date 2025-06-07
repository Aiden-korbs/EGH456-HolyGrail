
# Livelock

## What is Livelock?

- **Livelock** is when two or more tasks continuously change state in response to each other, but no useful progress is made.
- Unlike deadlock, tasks are not blocked—they remain active but “dancing around the problem.”

### Example

- Two tasks keep releasing and re-acquiring a lock to be polite (e.g., see the other wants it), but both just keep retrying endlessly.
- Real-world analogy: Two people trying to pass each other in a hallway, both stepping aside for the other, but never moving forward.

## In Code

```c
while(1) {
    if (try_acquire_resource()) {
        // Do work
        break;
    } else {
        // If resource unavailable, immediately retry or yield
        taskYIELD(); // If both do this, neither may ever get the lock!
    }
}
```
**Result:**  
Both tasks keep retrying and yielding to each other, but nothing gets done.
