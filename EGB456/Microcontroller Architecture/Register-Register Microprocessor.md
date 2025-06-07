**Example:**
	REG[r1] ← MEM[adrs_of_op1]     LDR  
	REG[r2] ← MEM[adrs_of_op2]     LDR  
	REG[r1] ← REG[r1] + REG[r2]    ADD  
	MEM[adrs_of_result] ← REG[r1]  STR  
	Register-Register Microprocessor Architecture:  
	(Note: This is different from a single accumulator)

	- LDR = Load Register
	- ADD = Add value of two registers
	- STR = Store Register

	Example:
		ADD R0, R1, R2 -> R1 + R2 STR R0
 
**M4 processors special purpose registers:**
	(See Section 2.3.3 Register Map in the TM4C1294 Datasheet)
	
	![[Screenshot 2025-03-12 at 8.49.59 PM.png|600]]
	