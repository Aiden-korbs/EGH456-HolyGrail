#### NVIC:
- Is a key hardware component of event driven and real-time system design
- Controls **all** exceptions and interrupts
- Provides the ability to:
	- Individually Enable/Disable interrupts for specific devices
	- Establishes relative priorities among various interrupts
		- Each interrupt is assigned a priority number (0-7) 0 being highest
- Level and pulse detection of interrupts
	- Pulse:
		- Triggered on a **short pulse**, usually the **rising edge** (signal goes from LOW → HIGH)
		- Only **one interrupt** is generated per pulse.
		- Once triggered, no need to manually clear the signal.
		- **NVIC behaviour:** Captures the event as soon as it detects the edge, then clears the pending flag when the ISR (interrupt service routine) runs.
	- Level:
		- Triggered when the signal **stays HIGH or LOW** (i.e. stays asserted).
		- Interrupt remains pending as long as the signal is active.
		- The interrupt **must be acknowledged or cleared** in software or hardware — or it will keep re-triggering.
		- **NVIC behaviour:** Keeps the interrupt pending if the line is still active **after** the ISR.
- Latches all interrupts
	- interrupts are pending and not lost
- Priorities, dynamic reprioritisation, grouping of priorities
	- Tail Chaining
- When software enters the ISR for that interrupt it goes form pending to active
	- interrupts are monitored while in the ISR
	- for pulsed interrupts the state can be pending and active

![[Screenshot 2025-03-24 at 9.57.10 PM.png|400]]