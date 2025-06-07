• Configures the operation of the device 
• Clock control, power control, reset control 
• Enables/Disables peripherals 
• Alternate function selects for pins 
• See Register Map Table 5-11 of technical reference manual 
• Useful API to system control in driverlib

#### System Control and GPIO Example:
	• Use system control to set clock freq (sysctl.h) 
```c
	SysCtlClockFreqSet(SYSCTL_OSC_INT | SYSCTL_USE_PLL | SYSCTL_CFG_VCO_320, 40000000);
```
	• Use system control to enable the particular port (sysctl.h)
```c
	SysCtlPeripheralEnable(SYSCTL_PERIPH_GPIOQ);
```
	• Configure the particular port pin to be direction ‘out’ ( gpio.h )
```c
	GPIOPinTypeGPIOOutput(GPIO_PORTQ_BASE, GPIO_PIN_7);
```
	• Use gpio driver to write to port
```c
	GPIOPinWrite(GPIO_PORTQ_BASE, GPIO_PIN_7, GPIO_PIN_7);
```
