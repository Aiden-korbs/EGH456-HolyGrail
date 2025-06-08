- Host/device topology (host = master)
    
- Differential pair lines (+ power, ground)
    
- USB 2.0: 480Mbps; 3.0: 5Gbps; 3.1: 10Gbps
    
- Frame-based protocol (typically 1ms per frame)
    
- Transaction types: Control, Isochronous, Bulk, Interrupt
    
- Packets: sync, PID, payload, EOP

**Transfer Types**

|Type|Use|Features|
|---|---|---|
|Control|Config, setup|Command info|
|Isochronous|Audio/video, streaming|Guaranteed time, no retry|
|Bulk|Large, non-time-critical data|Printers, scanners|
|Interrupt|Fast, small, periodic transfers|Keyboards, mice|
