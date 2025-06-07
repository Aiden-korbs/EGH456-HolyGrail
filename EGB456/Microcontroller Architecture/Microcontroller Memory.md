**Desktop Architecture:**
	![[Screenshot 2025-03-13 at 3.29.21 PM.png|400]]

**Embedded Processor Architecture:**
	Memory Mapped peripherals:
		- the input-output devices have addresses in the same space as memory.
		- The memory addresses for I/O devices are not used by program instructions and constants or variables.
		- ![[Screenshot 2025-03-13 at 3.31.31 PM.png|500]]

**4GB Memory Map:**
	![[Screenshot 2025-03-13 at 3.47.29 PM.png|550]]

**Bit Banding:**
	- Bit banding maps a *complete [word](<Basic Structure.md>#Word) of memory onto a single bit in the bit-band region
	- writing to one of the *alias words* will set or clear the corresponding bit in the bit-band region
	- allows individual bits to be toggled from C without performing RMW sequence of instructions
	- results in atomic operations to manipulate bits
		- An atomic operation is indivisible, meaning that once it starts, it runs to completion without being interrupted or interfered with by any other operation
	
	![[Screenshot 2025-03-13 at 3.52.55 PM.png]]



