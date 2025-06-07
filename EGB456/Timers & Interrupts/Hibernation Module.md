#### Manages removal and restoration of power for reducing system power.
- Puts CPU and peripherals into idle turning off power
- Can be woken up via external source or internal timer
	- 32 Bit RTC (Real Time Clock) counter register for seconds and a 15-bit sub seconds match
	- Can be configured for specifically timed wakeup
- RTC Calendar Function
	- Six internal Registers to store calendar values
		- Year, Month, Day, Day of the week, Hours, Minutes, Seconds
		- 24 hour or AM/PM configurations 
##### Schematic:
![[Screenshot 2025-03-22 at 9.06.07 PM.png|400]]