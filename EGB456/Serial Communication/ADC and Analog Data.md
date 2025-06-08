# ADC and Analog Data

- **ADC** (Analog-to-Digital Converter):  
  - Converts analog to digital for MCU processing.
- **TM4C MCU**:
  - 2 ADC modules, 20 analog channels, 12-bit resolution, 2M samples/sec max.
  - Can trigger by timer, PWM, comparator, software, etc.
- **Resolution**:  
  - 12 bits → 0–4095 range.
  - For 3.3V Vref: `3.3V / 4095 ≈ 0.806 mV/step`.

## Calibration

Use two known voltage references, calculate gain (m) and offset (c):

```
m = (Vref2 - Vref1) / (yH - yL)
c = Vref1 - m*yL
Vu = m*x + c
```