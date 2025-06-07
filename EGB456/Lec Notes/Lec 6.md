#### RTOS
Multi threading
- ISRs as short as possible (data collection)
- Threads do the work
Tasks and idle Task
- have independent stacks
ISR
- Share stack
Arbitration of SR
- **Modifying scheduler**
	- Disable interrupts
		- good for small critical sections
		- may miss important interrupts
	- Disable task switching
		- Blocks execution of all other threads
		- no protection of shared resources within ISR
- **Semaphores/Mutex**
