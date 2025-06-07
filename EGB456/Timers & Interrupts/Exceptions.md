#### Summary:
- Each exception has:
	- An exception number (0-255)
	- A priority level
	- An exception handler routine
	- An entry in the vector table
		- Program address of associated handler routine
		- By default, the vector table is stored starting at address 0
		- Can be relocated by changing vector table offset register (VTABLE)

##### Exception States:
- Inactive:
	- Is not active nor pending
- Pending:
	- Waiting to be serviced by processor
- Active:
	- An exception handler that is being serviced but not completed
	- An exception handler can interrupt the execution of another exception handler. This means both exceptions are in active state (incomplete)
- Active and Pending:
	- Is being serviced by processor and there is a pending exception form the same source
- ![[Screenshot 2025-03-24 at 9.08.25 PM.png|200]]

##### Exception Types (VTABLE):
| Exception Type | Vector Number | IRQ Number | Priority     | Comment                              |
|----------------|----------------|-------------|--------------|--------------------------------------|
| Reset          | 1              | -3          |              | Power up and warm reset              |
| NMI            | 2              | -14         | -2           | Non-Maskable Interrupt (NMI)         |
| Hard Fault     | 3              | -13         | -1           |                                      |
| Memory Mgmt    | 4              | -12         |              | Address/Memory-related faults        |
| Bus Fault      | 5              | -11         |              |                                      |
| Usage Fault    | 6              | -10         |              | Undefined instruction                |
| (Reserved)     | 7–10           |             |              | *Reserved*                           |
| SVCall         | 11             | -5          | Configurable | Software Interrupt (SVC instruction) |
| Debug Monitor  | 12             |             | Configurable |                                      |
| (Reserved)     | 13             |             |              |                                      |
| PendSV         | 14             | -2          | Configurable |                                      |
| SysTick        | 15             | -1          | Configurable | System Timer Tick                    |
| Interrupts     | ≥16            | ≥0          | Configurable | External; fed through NVIC          |
##### Exception Processing:
Following steps are followed when an exception is triggered:
1. [[Stacking]]
	1. Push contents of R0-R3,R12,PC,PSR,LR onto stack
	2. Functions do not have to save these registers when entering or returning (AAPCS)
2. Fetch Address
	1. Identify exception using PSR, bits 7:0 contains exception type
	2. Copy exception handler from VTABLE to PC (program counter)
3. Load Link Register (LR)
	1. Store current mode of CPU and stacking type to LR 4:0 (EXC_RETURN) for return
4. Enable Handler Mode
5. Execute Handler

![[Screenshot 2025-03-24 at 9.42.12 PM.png|300]]

![[Screenshot 2025-03-24 at 9.47.24 PM.png|400]]