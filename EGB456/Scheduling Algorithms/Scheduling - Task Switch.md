## What is Task/Thread Switching?

- In embedded and real-time operating systems (RTOS), software is divided into smaller execution units: **tasks (threads)** and **interrupts (ISRs)**, which all share the CPU.
    

## How Task Switching Works

- **Context switch**: When the CPU changes from running one task to another, saving the current state (registers, stack pointer, etc.) and loading the state of the next task.
    
- **Triggers for task switching:**
    
    - **Hardware Interrupt**: An external event (e.g., timer, GPIO input) causes the CPU to immediately pause the current task and execute a specific interrupt handler. After the ISR, the scheduler may choose a different task to run.
        
    - **Software Interrupt or Kernel Call**: A running task can voluntarily yield control, block on a resource, or make a system call that prompts a context switch.
        
    - **Periodic Timer Interrupt (SysTick/System Tick):** Many RTOS kernels use a regular timer interrupt to check if a higher-priority task is ready or to advance time-based scheduling (e.g., time slicing).
        

## Key Scheduling Decisions

- The **kernel scheduler** evaluates which task should run next, based on task priority, readiness, and system rules.
    
- After every interrupt or system event, the scheduler may decide to continue the current task or switch to a new one.
    

## Why It Matters

- **Responsiveness**: Fast, predictable task switching is critical for meeting deadlines and handling time-sensitive inputs (e.g., safety sensors).
    
- **Determinism**: Reliable scheduling ensures the system behaves the same way every time, essential for real-time control.
    

## Example

- If a button press triggers an interrupt while a sensor task is running, the CPU pauses the sensor task, runs the button ISR, and may resume a different (higher-priority) task afterwards.