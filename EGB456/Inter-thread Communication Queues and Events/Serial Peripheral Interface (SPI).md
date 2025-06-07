
# Serial Peripheral Interface (SPI)

SPI, part of [[Inter-Thread Communication]], characteristics:

- Full-duplex synchronous communication
- Master-slave topology with SS lines
- High throughput compared to [[Inter-Integrated Circuit (I2C)]]

Typical connections:
```
Master                 Slave
| MOSI ------> MOSI |
| MISO <------ MISO |
| SCLK ------> SCLK |
| SS   ------> SS   |
```
