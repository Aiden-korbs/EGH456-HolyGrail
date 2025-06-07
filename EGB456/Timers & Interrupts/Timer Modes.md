#### Edge Count Mode:
Edge count mode is typically used in counter/timer applications within microcontrollers. In this mode, the counter increments or decrements (based on configuration) each time a specified edge (rising or falling) is detected on an input signal. This mode is often used for:
- **Frequency Measurement**: By counting the number of edges over a set period, you can determine the frequency of an incoming signal.
- **Event Counting**: It is useful for counting events or occurrences, which are represented by transitions in a digital signal.
The functionality can vary slightly depending on the specific microcontroller architecture, but generally, the key aspects are:
- **Edge Detection**: Configurable to count on rising edges, falling edges, or both.  
- **Counter**: A register or variable that increments or decrements based on edge detections.

![[Screenshot 2025-03-22 at 8.12.09 PM.png]]

#### PWM Mode:
PWM mode is used to generate a digital signal with a variable duty cycle, which is the proportion of time the signal is high (on) as compared to being low (off). This mode is crucial in control systems and is often used for:
- **Motor Control**: Adjusting the speed of DC motors by varying the duty cycle of the control signals.
- **LED Dimming**: Controlling the brightness of LEDs by changing the duty cycle of the power signal.
- **Signal Generation**: Creating a more complex waveform for various applications, including audio signals or light patterns.

In PWM mode, the key parameters are:
- **Duty Cycle**: Defines how long the signal stays high in each cycle. For instance, a 50% duty cycle means the signal is high for half of the time and low for the other half. 
- **Frequency**: The rate at which the PWM signal completes one period (one full cycle of high and low).
- **Resolution**: Determines how finely the duty cycle can be adjusted, typically defined by the number of bits of the timer.
##### Code Example:
```c
uint32_t ui32SysClock; ui32SysClock = SysCtlClockFreqSet((SYSCTL_XTAL_25MHZ | SYSCTL_OSC_MAIN | SYSCTL_USE_PLL | SYSCTL_CFG_VCO_480), 120000000); 
// Run from the PLL at 120 MHz. 
SysCtlPeripheralEnable(SYSCTL_PERIPH_TIMER0); // Enable the Timer 0 Module. 
TimerConfigure(TIMER0_BASE, TIMER_CFG_PERIODIC); 
// Configure the timer in periodic mode and full width (32 bits). 
TimerLoadSet(TIMER0_BASE, TIMER_A, ui32SysClock); // Load the timer value 
TimerEnable(TIMER0_BASE, TIMER_A); // Enable the timer.
```

![[Screenshot 2025-03-22 at 8.15.33 PM.png]]