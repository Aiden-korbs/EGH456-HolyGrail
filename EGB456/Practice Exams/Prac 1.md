**INSTRUCTIONS:** Attempt all questions. Marks are allocated as indicated. Write clearly and show all working. Diagrams and code provided where applicable.

---

## Question 1 (1 mark)

In your own words define what an embedded system is and discuss two common design requirements for such systems.

---

## Question 2 (1 mark)

Define the difference between a soft real-time and hard real-time system and give an example of each.

---

## Question 3 (1 mark)

Describe two different models used in FreeRTOS for thread intercommunication and name one kernel object for each.

---

## Question 4 (1 mark)

Fill in the return type and argument types for the Tiva C Series function below:

```c
________ GPIODirModeGet(________);
```

---

## Question 5 (2 marks)

An accelerometer connected via I2C runs at 1 MHz. A single read includes:

- 8 bits for command
- 8 bits for register address
- 16 bits of data

**(a)** How many bits are transmitted per read?  
**(b)** How long does one transfer take?

---

## Question 6 (2 marks)

Compare and contrast queues and semaphores in FreeRTOS. Provide an example use case for each.

---

## Question 7 (2 marks)

Consider the following task code using two mutexes:

```c
void TaskA(void *pvParameters) {
    for (;;) {
        xSemaphoreTake(mutexA, portMAX_DELAY);
        xSemaphoreTake(mutexB, portMAX_DELAY);
        // critical section
        xSemaphoreGive(mutexB);
        xSemaphoreGive(mutexA);
    }
}

void TaskB(void *pvParameters) {
    for (;;) {
        xSemaphoreTake(mutexB, portMAX_DELAY);
        xSemaphoreTake(mutexA, portMAX_DELAY);
        // critical section
        xSemaphoreGive(mutexA);
        xSemaphoreGive(mutexB);
    }
}
```

**(a)** What problem can occur?  
**(b)** How can this be prevented?

---

## Question 8 (2 marks)

Given three periodic tasks:

- Task A: Period 30ms, Execution 6ms  
- Task B: Period 60ms, Execution 10ms  
- Task C: Period 120ms, Execution 20ms

**(a)** Calculate CPU utilization  
**(b)** Can they be scheduled using Rate Monotonic Scheduling?

---

## Question 9 (1 mark)

Explain priority inversion and how priority inheritance helps resolve it. Provide a small example scenario.

---

## Question 10 (2 marks)

An ISR is used to detect a button press on the Tiva C Series. Describe a typical ISR setup and how it communicates with a FreeRTOS task.

---

## Question 11 (2 marks)

The OPT3001 sensor configuration register is set to `0xCA10`.

**(a)** Convert to binary  
**(b)** Interpret the configuration:
- Range setting
- Conversion time
- Operating mode
- INT pin polarity

**Reference diagram:**  
![OPT3001 Config Diagram](https://upload.wikimedia.org/wikipedia/commons/thumb/1/14/I2C.svg/320px-I2C.svg.png)

---

## Question 12 (2 marks)

What is a race condition? Provide a code example using FreeRTOS and explain how to prevent it.

---

## Question 13 (1 mark)

Describe the differences between cooperative and preemptive scheduling. Which is better for real-time applications and why?

---

## Question 14 (2 marks)

Write a FreeRTOS trace macro that logs task switches. What output would you expect when three tasks of equal priority are running?

```c
#define traceTASK_SWITCHED_IN()  
UARTprintf("Task Switched In: %s\n", pcTaskGetName(NULL));
```

---

## Question 15 (2 marks)

A FreeRTOS system has the following scheduling diagram:

**Diagram:**
```
Time (ms):     0   10   20   30   40   50
Task A       [===][===][===]
Task B               [===][===]
Task C                        [===][===]
```

**(a)** What is the CPU utilization?  
**(b)** Could all tasks meet their deadline using RMS?

---

