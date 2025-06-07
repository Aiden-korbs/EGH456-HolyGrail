- System Clock (SysClk)
	- Clock signal that is distributed to the CPU
	- Based on clock source and divisor factor
- Precision Internal Oscillator (PIOSC)
	- Enabled on power-up, 16Mhz, SYSCTL_OSC_INT
- Main Oscillator (MOSC)
	- External XTAL, 5-25Mhz, SYSCTL_OSC_MAIN
- Phase Locked Loop (PLL)
	- Disabled by default on power on
	- Generates clock frequency faster than the source clock (PIOSC, MOSC)
	- Two output frequencies (320 or 480 Mhz)
- ![[Screenshot 2025-03-17 at 9.27.11 PM.png|400]]
#### Setting System Clock:
- **Select** Oscillator source, system clock source, Desired freq
- **Example:** Configure the system clock to be 40 MHz with a 320-MHz PLL setting using the 16-MHz internal oscillator.
	- SysCtlClockFreqSet -> System Control Module – For clock settings, reset control, power control and [[Watchdog Timer|Non-Maskable Interrupt (NMI) control]].
```c
ui32clockFreq = SysCtlClockFreqSet(SYSCTL_OSC_INT | SYSCTL_USE_PLL |  
SYSCTL_CFG_VCO_320, 40000000);
```
- **Returns:** The actual configured system clock frequency in Hz or zero if the value could not be changed due to a parameter error or PLL lock failure.