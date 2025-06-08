- Sometimes need to wait on _multiple_ conditions (not just one flag)
    
- Semaphore: waits on one flag only
    
- Events: can wait for combinations (OR, AND) of multiple events
    

#### **FreeRTOS Event Groups**

- 32 bits, 24 LSB used for events
    
- Tasks/ISRs set/clear/wait on event bits

```c
EventGroupHandle_t xEventGroup = xEventGroupCreate();
xEventGroupSetBits(xEventGroup, BIT_0 | BIT_1);

EventBits_t uxBits = xEventGroupWaitBits(
    xEventGroup,
    BIT_0 | BIT_1,     // Wait for these
    pdTRUE,            // Clear on exit
    pdTRUE,            // Wait for all bits (AND)
    portMAX_DELAY      // No timeout
);
```
- From ISR: use `xEventGroupSetBitsFromISR`
    

#### **Example: Wait for ANY Event**
```c
#define EVENT_0 (1 << 0)
#define EVENT_4 (1 << 4)
void waitForEitherEvent(EventGroupHandle_t xEventGroup) {
    EventBits_t uxBits;
    uxBits = xEventGroupWaitBits(xEventGroup, EVENT_0 | EVENT_4, pdTRUE, pdFALSE, pdMS_TO_TICKS(100));
    // pdFALSE: ANY (OR), pdTRUE: ALL (AND)
    // Handle event bits here
}
```
