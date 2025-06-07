#### Task A:
1. It results in the UART print corrupting, merging each tasks output e.g:
	1. econdary Task RunniHnegl!l o
2. It now follows a predictable outcome with no corrupting of the shared resource:
	2. Secondary Task Running! 
		Hello world! 
		Secondary Task Running! 
		Hello world! 
		Hello world!
3. That only the task with highest priority (Secondary) is printing. This is most likely due to the fact that the scheduler has to operate on higher priority tasks first which would be executed and called again before the next priority task can run which then leads to it being paused indefinitely
#### Task B:
1. It blocks the task from being executed at all until the interrupt receives and input from the button which then sends a semaphore basically giving the task the go ahead to run.