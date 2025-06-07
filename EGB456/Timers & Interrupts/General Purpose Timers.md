- General Purpose Timers are up/down counters
	- Useful to time or count external events
	- Default is down counter
- The counters are clocked by the system clock or alternative sources
- Operate in one shot or periodic mode
	- "one-shot" mode triggers a callback function only once after a specified delay, while "periodic" mode triggers the callback function repeatedly at a set interval until stopped
- Useful for
	- repsond to or generate interrupts
	- triggering ADC events
	- Generating signals (PWM)
	- Handling/Counting input signals (GPIO, encoders, data, etc)

#### Counters/Timers
![[Screenshot 2025-03-17 at 9.19.49 PM.png|400]]

