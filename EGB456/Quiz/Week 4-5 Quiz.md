##### Task A:
1. Used as a macro for hardware access. Is safe to use in the timer due to the volatile data type it tells the compiler that the value of the variable may change at any time not necessarily by the code its currently working on.
2. Due to the interrupts occurring in a set frequency (hz) 
3. When a timer has reached its specified value it tells the interrupt controller to start a specific ISR
4. It would come down to prioritising the interrupts if one interrupt has higher priority it goes first or, one of the interrupts become a pending exception to processed by the microcontroller next. If two interrupts have the same priority the one with the lowest vector address gets prioritised
##### Task B:
1. They are both because some methods are using software based IntPrioritySet(INT_GPIOA, 0x00); and others are using hardware such as Triggering the interrupts: HWREG(NVIC_SW_TRIG) = INT_GPIOC - 16;
	1. HWREG is actually a software
2. Tail chaining essentially skips the state saving and restoring after an ISR is completed if a higher priority ISRs handler is waiting for the previous one to finish. This shortens the overhead between interrupts saving a bit of time
3. It leads to GPIO B to be executed first which throws the error priority fail as they are not in the expected order of A > B > C instead B > A> C or B > C > A
##### Task C:
1. Essentially used to regain control of a system when it has failed, could be from software or external failure. Just resets the whole system.