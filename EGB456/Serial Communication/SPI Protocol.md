# SPI Protocol

- Full duplex, synchronous.
- Master-slave: master controls frame, each slave has own SS line.
- Data: MOSI (out), MISO (in).
- Pros: High throughput, protocol flexible, fewer pull-ups.
- Cons: More pins/lines, no hardware error checking, only one master.