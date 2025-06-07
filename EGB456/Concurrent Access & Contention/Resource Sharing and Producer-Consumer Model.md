
## Producer–Consumer Model (Previous Lecture)

- Thread 1: Produces a buffer or message, puts it in a container.
    
- Thread 2: Blocks until data is available, then consumes it.
    
- Simple structured protocol—no contention if managed correctly.
    

![](https://chatgpt.com/c/producer_consumer.png)

## Transition to Concurrent Access

- Concurrent access allows _any_ thread to access _any_ resource at _any_ time.
    

[[Concurrent Access Model]]