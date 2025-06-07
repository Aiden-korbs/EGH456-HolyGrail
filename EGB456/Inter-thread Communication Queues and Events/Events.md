
# Events

Events in [[Inter-Thread Communication]]:

- Tasks block until specific events occur
- Event Groups with flags for tracking

Creating an event group:
```c
EventGroupHandle_t xEventGroup = xEventGroupCreate();
```

Setting event bits:
```c
xEventGroupSetBits(xEventGroup, EVENT_BIT);
```

Waiting on event bits:
```c
xEventGroupWaitBits(xEventGroup, EVENT_BIT, pdTRUE, pdFALSE, timeout);
```
Complements message passing with [[Queues]]
