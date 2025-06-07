[[Microcontroller Architecture]]
	- Arm Cortex M uses a 3-address architecture
		(Op Code + up to 3 registers (operand))
	- Each processor design has its own set of instructions

**ARM Cortex M4 instruction set**
	- There is a mnemonic for each instruction set which is used by assembly
		- Example: STR, ADD, LDR
	- There one or more operands usually up to 3
		- Example: ADD R0, R1, R2 has 3 operands and an instruction set
	- Flags may be set to indicate carry, zero, overflow, negative
	
	![[Screenshot 2025-03-13 at 2.49.36 PM.png]]


**ARM vs Thumb Instruction Sets:**
	- Arm instructions:
		- 32 Bit instructions (4 Bytes)
		- Improved processor execution over Thumb Instructions
	- Thumb Instructions:
		- 16 Bit instructions (2 Bytes)
		- Improved code density over ARM (Less memory used)
	- Thumb2 Instructions:
		- 16 and 32 Bit instructions
		- Is a superset of thumb instructions (includes all thumb instructions + 32 Bit instructions)
		- The 32-bit instructions created in a way that the leading 16-bits are different from all 16-bit Thumb instructions

- **Example:**
	Consider a program that involves 6 operations composed of: 
		• 3 simple operations 
		• 3 complex operations 
	The 3 simple operations can be performed by: 
		• 3 ARM Instructions (i.e. 1 instruction each), or 
		• 3 Thumb Instructions 
	The 3 complex operations can be performed by: 
		• 3 ARM Instructions, or 
		• 6 Thumb Instructions (i.e., 2 instructions per operation) 
		
	Assuming that all instructions take 1 clock cycle to execute what is the entire program size and execution time for 1. ARM Instruction implementation? 2. Thumb Instruction implementation?
	**Answer:**
		ARM instruction:
			(4bytes x 3) + (4bytes x 3) = 24 bytes @ 6 clock cycles
		Thumb instruction:
			(2Bytes x 3) + (2Bytes x (3x2)) = 18 bytes @ 9 clock cycles

**Instruction Set - Multiple Formats:    Data Processing:**
![[Screenshot 2025-03-13 at 3.14.30 PM.png|350]]![[Screenshot 2025-03-13 at 3.15.21 PM.png|300]]

**Cortex-M Instruction Sets:**
![[Screenshot 2025-03-13 at 3.21.39 PM.png]]