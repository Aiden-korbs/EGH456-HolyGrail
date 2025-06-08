# Universal Asynchronous Receiver Transmitter (UART)

- Handles parallel-to-serial and serial-to-parallel conversion.
- Internal shift, data, status, and control registers.
- Can generate interrupts after RX/TX.

## Parameters

- Clock speed/baud rate.
- Data bits length.
- Stop bits (start/stop for sync).
- Optional parity (even/odd) for error detection.
- **Baud rates**: 1200, 2400, 4800, 9600, 19200, 38400, 57600, 115200, etc.

## UARTs on TM4C1294

- 8 UARTs, each with 16x8 FIFO buffers for RX/TX.
- Parity, data bits, and stop bits configurable.
- Can generate interrupts at multiple FIFO levels.
- *Tivaware*: `driverlib/uart.c`, `utils/uartstdio.c` for APIs.