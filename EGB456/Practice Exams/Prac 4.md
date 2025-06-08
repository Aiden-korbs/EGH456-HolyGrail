
**INSTRUCTIONS:** Attempt all questions. Part marks are available. Show working where required.

## Question 1 (1 mark)

In your own words define what an embedded system is and discuss two common design requirements for such systems.


## Question 2 (1 mark)

Define the difference between a soft real-time and hard real-time system and give an example of each.


## Question 3 (1 mark)

Describe the two different models used in FreeRTOS for thread intercommunication and indicate one FreeRTOS kernel object that can be used to implement each model.


## Question 4 (1 mark)

Fill in the correct return type and arguments for the GPIO function:

```c
________ GPIODirModeGet(________);
```


## Question 5 (3 marks)

An accelerometer sends 3-axis data via I2C (1500 bps), using GPIO interrupts per axis. Each ISR adds 50 clock cycles overhead. The CPU runs at 10 MHz and each read includes 8 bits address + 8 bits register + 16 bits data.

(a) Calculate time to read 1 axis (in microseconds).
(b) Can the system achieve 120Hz per axis?


## Question 6 (3 marks)

Refer to the simplified accumulator processor diagram:

(a) What is the accumulator value after the second instruction?
(b) What is the value at memory location 4 after all instructions?
(c) What is the word size of the processor?


## Question 7 (2 marks)

Review the following init function and I2C setup:

```c
SysCtlPeripheralEnable(I2C0_SYSCTL_PERIPH);
SysCtlPeripheralEnable(SYSCTL_PERIPH_GPIOB);
GPIOPinConfigure(GPIO_PB2_I2C0SCL);
GPIOPinConfigure(GPIO_PB3_I2C0SDA);
GPIOPinTypeI2CSCL(I2C0_GPIO_PORT, I2C0_SCL_PIN);
GPIOPinTypeI2C(I2C0_GPIO_PORT, I2C0_SDA_PIN);
I2CMasterInitExpClk(I2C0_BASE, SysCtlClockGet(), false);
IntEnable(I2C0_BASE);
IntRegister(INT_I2C0, I2CHandler);
```
(a) What peripheral is being initialized?
(b) Identify and explain a potential issue in this code.


## Question 8 (2 marks)

OPT3001 sensor config register is set to 0xCA10. Interpret:
(a) Range setting
(b) Conversion time
(c) Operating mode
(d) INT pin polarity


## Question 9 (2 marks)

Describe the potential issue in the following FreeRTOS code involving two tasks sharing two semaphores.
```c
SemaphoreHandle_t xSemaphoreA, xSemaphoreB;
void Task1() {
  xSemaphoreTake(xSemaphoreA, portMAX_DELAY);
  xSemaphoreTake(xSemaphoreB, portMAX_DELAY);
  // do stuff
  xSemaphoreGive(xSemaphoreB);
  xSemaphoreGive(xSemaphoreA);
}
void Task2() {
  xSemaphoreTake(xSemaphoreB, portMAX_DELAY);
  xSemaphoreTake(xSemaphoreA, portMAX_DELAY);
  // do stuff
  xSemaphoreGive(xSemaphoreA);
  xSemaphoreGive(xSemaphoreB);
}
```


## Question 10 (2 marks)

Explain what is meant by bounded vs unbounded priority inversion. Give one scenario example of each.

