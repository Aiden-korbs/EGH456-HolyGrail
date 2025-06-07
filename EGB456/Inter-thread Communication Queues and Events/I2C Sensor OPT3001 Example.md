
# I2C Sensor OPT3001 Example

Covered in [[Inter-Thread Communication]], steps include:

1. Initialize I2C:
```c
I2C_Init(slaveAddress, clockSpeed);
```

2. Configure sensor:
```c
I2C_WriteRegister(OPT3001_CONFIG_REG, configData);
```

3. Read data:
```c
I2C_Write(OPT3001_DATA_REG);
data = I2C_Read();
```
Related Protocol: [[Inter-Integrated Circuit (I2C) Protocol]]
