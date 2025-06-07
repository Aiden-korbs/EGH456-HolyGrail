
# Queues

Queues in [[Inter-Thread Communication]]:

- FIFO data structure for inter-thread communication
- Blocking operations on full/empty conditions

Sending example:
```c
xQueueSend(queueHandle, &data, timeoutTicks);
```

Receiving example:
```c
xQueueReceive(queueHandle, &data, timeoutTicks);
```
Related synchronization: [[Events]]
