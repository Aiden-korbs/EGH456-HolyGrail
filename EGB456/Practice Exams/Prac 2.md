**INSTRUCTIONS:** Attempt all questions. Show all working.

## Question 1 (1 mark)

Explain the role of the tick timer in FreeRTOS. How does it influence task delays and context switching?


## Question 2 (2 marks)

Using an annotated diagram, describe the transitions between all task states in FreeRTOS (e.g. Ready, Running, Blocked, Suspended, Deleted).


## Question 3 (2 marks)

A system has 4 periodic tasks. Task execution times and periods are given below:

- Task A: Exec = 3ms, Period = 15ms
- Task B: Exec = 5ms, Period = 20ms
- Task C: Exec = 2ms, Period = 10ms
- Task D: Exec = 1ms, Period = 25ms

**(a)** Calculate CPU utilization.
**(b)** Use the schedulability test to determine if RMS is suitable.


## Question 4 (2 marks)

Describe how `vApplicationIdleHook()` can be used in a power-efficient embedded application.
Provide example pseudocode showing its integration.


## Question 5 (2 marks)

Given the following I2C write sequence to a sensor register:
`Start -> 0x50 (W) -> 0x01 -> 0x23 -> Stop`

**(a)** Break down each byte.
**(b)** What does this command do if 0x01 is a configuration register?


## Question 6 (1 mark)

What is meant by 'hook macros' in FreeRTOS? List two hooks and describe how developers use them.


## Question 7 (2 marks)

Given the following memory map of a system:

- 0x0000–0x1FFF: Bootloader
- 0x2000–0x3FFF: Application code
- 0x4000–0x4FFF: Peripheral registers

Explain why access to 0x4000 requires careful timing and how interrupts affect this.


## Question 8 (2 marks)

The following code reads a button and toggles an LED using GPIO:
```c
if(GPIOPinRead(GPIO_PORTF_BASE, GPIO_PIN_4) == 0) {
    GPIOPinWrite(GPIO_PORTF_BASE, GPIO_PIN_1, GPIO_PIN_1);
}
```
**(a)** What hardware behavior does this code produce?
**(b)** What might go wrong in an RTOS system if this runs in a task?


## Question 9 (1 mark)

Explain the difference between `vTaskDelay()` and `vTaskDelayUntil()`. Give a scenario where each is more appropriate.


## Question 10 (2 marks)

What is a 'phantom priority inversion'? How is it different from traditional priority inversion?
Can it be resolved with priority inheritance?


## Question 11 (2 marks)

Consider this code for an ISR communicating with a task:
```c
void ISR_Handler(void) {
    BaseType_t xHigherPriorityTaskWoken = pdFALSE;
    vTaskNotifyGiveFromISR(TaskHandle, &xHigherPriorityTaskWoken);
    portYIELD_FROM_ISR(xHigherPriorityTaskWoken);
}
```
Explain the purpose of `portYIELD_FROM_ISR()` and what happens if it’s omitted.

