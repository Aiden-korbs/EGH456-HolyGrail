- Multiple threads may need access to the same data
    
- **Problems:**
    
    - Data corruption, inconsistent state
        
    - Pre-emption risks
        
- **Solutions:**
    
    - Use globals (unsafe)
        
    - Use synchronization: Mutex, Semaphore
        
    - Use message passing (queues, events)