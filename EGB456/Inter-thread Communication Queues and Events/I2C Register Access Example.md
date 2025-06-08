#### Sensor OPT3001 Example:

1. **Initialise**
    
    - Setup master, slave address, clock speed
        
2. **Configure Sensor**
    
    - Write config registers
        
3. **Read Sensor**
    
    - Point to data register, read
        

#### 16-bit Register Write Example

c

CopyEdit
```c
// Write 0x10C4 to register 0x01 (OPT3001) 
I2C_Write(slave_addr, reg_addr, 0x10C4);
```

- Transmission order:
    
    1. Slave Address
        
    2. Register Address
        
    3. Data MSB
        
    4. Data LSB