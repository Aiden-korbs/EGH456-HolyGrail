#### **Passing by Value**
```c
struct MsgObj {
    uint8_t id;
    uint8_t val;
};

QueueHandle_t xQueue;

void writerTask(int id) {
    struct MsgObj xMsgObj = {.id = 0xAA, .val = 0};
    for(;;) {
        xQueueSend(xQueue, &xMsgObj, 10);
        vTaskDelay(pdMS_TO_TICKS(1000));
        xMsgObj.val++;
    }
}
```

#### **Passing by Pointer (with malloc)**
```c
void writerTask(int id) {
    struct MsgObj *ptrMsgObj;
    for(;;) {
        ptrMsgObj = pvPortMalloc(sizeof(struct MsgObj));
        ptrMsgObj->id = 0xAA;
        ptrMsgObj->val = 0;
        if(xQueueSend(xPointerQueue, &ptrMsgObj, 10) != pdPASS) {
            vPortFree(ptrMsgObj);
        }
        vTaskDelay(pdMS_TO_TICKS(1000));
    }
}
```

#### **Reader Freeing Memory**
```c
void readerTask() {
    struct MsgObj *xPtrReadMsgObj;
    for(;;) {
        if(xQueueReceive(xPointerQueue, &xPtrReadMsgObj, 10) == pdPASS) {
            UARTPrintf("Message %d from task %d\n", xPtrReadMsgObj->val, xPtrReadMsgObj->id);
            vPortFree(xPtrReadMsgObj);
        }
    }
}
```
Be careful: _malloc’d_ memory must be freed by the receiver