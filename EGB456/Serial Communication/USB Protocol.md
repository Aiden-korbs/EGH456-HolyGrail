# USB Protocol

- Industry standard since 1990s.
- Replaced most serial/parallel connections.
- Differential signal, host/device topology.
- USB 2.0: 480MB/s; USB 3.0: 5GB/s; USB 3.1: 10GB/s.
- 4 wires + shield (2 data, 1 power, 1 ground).
- **Transactions:** Control, Isochronous (streaming), Bulk (big transfers), Interrupt (fast/small).
- Frame-based, packets with sync, PID, payload, EOP fields.