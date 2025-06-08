**INSTRUCTIONS:** Attempt all questions. Show your working. Marks are shown per question.

## Question 1 (1 mark)

Define a real-time operating system (RTOS). List and describe two unique features that distinguish an RTOS from a general-purpose operating system.


## Question 2 (2 marks)

Consider the following code snippet for GPIO initialization on a Tiva C Series microcontroller:
```c
SysCtlPeripheralEnable(SYSCTL_PERIPH_GPIOF);
GPIOPinTypeGPIOOutput(GPIO_PORTF_BASE, GPIO_PIN_2);
```
(a) What does this code do?
(b) Describe how this could be modified to create an input pin with interrupt handling.


## Question 3 (2 marks)

The FreeRTOS scheduler uses a tick interrupt to manage task switching.
(a) If configTICK_RATE_HZ is set to 1000, how many ticks occur per second?
(b) Describe how this tick affects task delay functions like `vTaskDelayUntil()`.


## Question 4 (2 marks)

The following diagram shows a memory-mapped processor design with separate areas for bootloader, application, and peripheral registers.

**Draw a labelled diagram** of the memory space including ranges for:
- Bootloader
- Application Code
- I/O Peripheral Registers

Explain why access timing to peripheral registers is critical in an RTOS system.


## Question 5 (2 marks)

In FreeRTOS, tasks can exist in several states. Complete the following diagram and label all transitions between states: Ready, Running, Blocked, Suspended, Deleted. Describe one real-world event that causes each transition.


## Question 6 (2 marks)

The OPT3001 light sensor is configured via I2C. The configuration register is set to 0xCA10.
Using the register format documentation:
- Interpret the range setting.
- Interpret the conversion time and mode.
- What is the polarity of the INT pin?


## Question 7 (2 marks)

The following FreeRTOS code uses two semaphores for inter-task synchronization:
```c
xSemaphoreTake(mutexA, portMAX_DELAY);
xSemaphoreTake(mutexB, portMAX_DELAY);
// critical section
xSemaphoreGive(mutexB);
xSemaphoreGive(mutexA);
```
(a) What problem could arise if another task takes the semaphores in reverse order?
(b) Propose a solution.


## Question 8 (2 marks)

Three periodic tasks are defined with the following characteristics:
- Task 1: Period = 40ms, Execution = 10ms
- Task 2: Period = 80ms, Execution = 15ms
- Task 3: Period = 160ms, Execution = 30ms
(a) Compute the CPU utilization.
(b) Is the system schedulable using rate monotonic scheduling?


## Question 9 (1 mark)

Explain how `traceTASK_SWITCHED_IN()` and `traceTASK_SWITCHED_OUT()` macros can be used for debugging. Give a short example of logging output from these hooks.


## Question 10 (2 marks)

A FreeRTOS application has a race condition due to shared access to a global variable. Give a short code example and explain how to fix it using either mutexes or task notifications.


## Question 11 (2 marks)

Describe the mechanism of priority inheritance in FreeRTOS. Provide a short scenario and explain how the system behaves with and without inheritance enabled.


## Question 12 (2 marks)

In an embedded system using FreeRTOS, a task is deleted with `vTaskDelete(NULL);`.
(a) What happens to the task’s resources?
(b) When should a task use this function?

