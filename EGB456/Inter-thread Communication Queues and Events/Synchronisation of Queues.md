
- Queues use semaphores internally for sync
    
- If `xQueueReceive` on empty queue, task blocks
    
- If `xQueueSend` on full queue, task blocks
    
- Use `xQueueSendFromISR`/`xQueueReceiveFromISR` for interrupt context