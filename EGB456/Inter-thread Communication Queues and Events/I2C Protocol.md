- Multi-master, multi-slave
    
- Half duplex, synchronous
    
- Short distance, low speed
    
- 2 wires: **SCL** (Clock), **SDA** (Data)
    
- **Open drain**: Slaves pull low, can’t drive high
    

#### Protocol details:

- Device handles:
    
    - Start/stop condition
        
    - Address frame (7 bits + R/W), Data frame
        
    - ACK/NACK (1 = no response)
        
- Usually write register address, then data
    
- Often used for sensors (register based)

![[Screenshot 2025-06-08 at 11.13.57 am.png]]