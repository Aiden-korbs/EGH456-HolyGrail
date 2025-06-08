# I2C Protocol

- Multi-master, multi-slave, half-duplex, synchronous.
- Short range, two wires (SCL, SDA), open drain.
- Start/stop condition, 7-bit address + R/W, data frame, ACK/NACK.
- **Example** (Tivaware setup):

    ```c
    SysCtlPeripheralEnable(SYSCTL_PERIPH_I2C0);
    SysCtlPeripheralEnable(SYSCTL_PERIPH_GPIOB);

    GPIOPinConfigure(GPIO_PB2_I2C0SCL);
    GPIOPinConfigure(GPIO_PB3_I2C0SDA);

    GPIOPinTypeI2CSCL(GPIO_PORTB_BASE, GPIO_PIN_2);
    GPIOPinTypeI2C(GPIO_PORTB_BASE, GPIO_PIN_3);

    I2CMasterInitExpClk(I2C0_BASE, SysCtlClockGet(), false);
    ```

## I2C Read Example

```c
bool readI2C(uint8_t ui8Addr, uint8_t ui8Reg, uint8_t *data) {
    I2CMasterSlaveAddrSet(I2C0_BASE, ui8Addr, false);
    I2CMasterDataPut(I2C0_BASE, ui8Reg);
    I2CMasterControl(I2C0_BASE, I2C_MASTER_CMD_SINGLE_SEND);
    while(I2CMasterBusy(I2C0_BASE)) {}
    I2CMasterSlaveAddrSet(I2C0_BASE, ui8Addr, true);
    I2CMasterControl(I2C0_BASE, I2C_MASTER_CMD_BURST_RECEIVE_START);
    while(I2CMasterBusy(I2C0_BASE)) {}
    data[0] = I2CMasterDataGet(I2C0_BASE);
    I2CMasterControl(I2C0_BASE, I2C_MASTER_CMD_BURST_RECEIVE_FINISH);
    while(I2CMasterBusy(I2C0_BASE)) {}
    data[1] = I2CMasterDataGet(I2C0_BASE);
    return true;
}
```