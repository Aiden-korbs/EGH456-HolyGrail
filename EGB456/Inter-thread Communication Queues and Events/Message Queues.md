
- FreeRTOS object: fixed size, FIFO
    
- Send/receive values or structs
    
- Data is _copied_ on send
    
- Tasks can block if queue is full/empty
    
- Must have `configSUPPORT_DYNAMIC_ALLOCATION` enabled

```c
xQueueSend();
xQueueReceive();
```

[[Message Queues - Usage Example]]