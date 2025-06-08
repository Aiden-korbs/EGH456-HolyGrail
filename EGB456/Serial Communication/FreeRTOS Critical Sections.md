# FreeRTOS Critical Sections

- **Purpose**: Temporarily disable interrupts to protect shared resources for short code blocks.
- **Do not**: Call blocking functions (e.g., `vTaskDelay()`) inside a critical section.
- **Example**:
    ```c
    volatile uint32_t shared_counter = 0;

    void ISR_Handler(void) {
      shared_counter++;
    }

    void vTaskFunction(void *pvParameters) {
      for (;;) {
        taskENTER_CRITICAL();
        uint32_t copy = shared_counter;
        taskEXIT_CRITICAL();
        printf("Count: %lu\n", copy);
        vTaskDelay(pdMS_TO_TICKS(100));
      }
    }
    ```