#### Summary:
- Merriam-Webster:
	- "to break the uniformity or continuity of"
- Informs a program of some external event
- Breaks execution flow
	- CPU finishes the current instruction before going into the interrupt processing routine

#### Example Code (Timer Interrupt):
```c
uint32_t ui32SysClock;

// Set system clock to 120 MHz using PLL with 25 MHz external crystal
ui32SysClock = SysCtlClockFreqSet(
    SYSCTL_XTAL_25MHZ | SYSCTL_OSC_MAIN | SYSCTL_USE_PLL | SYSCTL_CFG_VCO_480, 
    120000000
);

// Enable Timer 0 peripheral
SysCtlPeripheralEnable(SYSCTL_PERIPH_TIMER0);
// Enable master interrupts globally
IntMasterEnable();
// Configure Timer 0 as a 32-bit periodic timer
TimerConfigure(TIMER0_BASE, TIMER_CFG_PERIODIC);
// Set the timer load value for 1-second delay (based on 120 MHz system clock)
TimerLoadSet(TIMER0_BASE, TIMER_A, ui32SysClock);
// Register the Timer 0 interrupt handler
TimerIntRegister(TIMER0_BASE, TIMER_A, Timer0IntHandler);
// Enable the timer interrupt
TimerIntEnable(TIMER0_BASE, TIMER_TIMA_TIMEOUT);
// Start the timer
TimerEnable(TIMER0_BASE, TIMER_A);

// Interrupt Service Routine (ISR) for Timer 0
void Timer0IntHandler(void) {
    // Clear the interrupt flag to acknowledge the interrupt
    TimerIntClear(TIMER0_BASE, TIMER_TIMA_TIMEOUT);
    // Optionally disable and re-enable global interrupts during critical section
    IntMasterDisable();
    // Toggle GPIO pin Q7 (e.g., blink an LED)
    GPIO_PORTQ_DATA_R ^= GPIO_PIN_7;
    IntMasterEnable();
}
```

##### Interrupt Example:
- Enabling interrupts (Uses CPSIE instruction)
	- Ensure global interrupts enabled:
		```c
	#include "driverlib/interrupt.h"
	IntMasterEnable(); // Enable Master Interrupts
	```
	- Also ensure peripheral device interrupt is enabled:
	```c
	TimerIntRegister(TIMER0_BASE, TIMER_A, Timer0IntHandler);
	TimerIntEnable(TIMER0_BASE, TIMER_TIMA_TIMEOUT);
```
- See interrupt.c in interrupts project
- This shows capabilities of [[Nested Vector Interrupt Controller (NVIC)|NVIC]]

