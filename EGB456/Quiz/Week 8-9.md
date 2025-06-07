#### Task A:
1. I2C 0 and GPIO port B and GPIO pins 2 & 3
2. Bits 15:12 control the Range Number Field which in this case is set to 0xC or 1100b for automatic full-scale setting mode with a conversion time of 100ms set by bit 11 of value 0
3. The high byte is received first as it is the most significant byte its important mostly because the OPT3001 expects it first.
4. It reads both the manufacturer id and device id registers (0x7E, 0x7F) and validates they are the expected result of 0x5449 and 0x3001 respectively 

#### Task D:
- Setup the sensor high and low limit registers, which are used to generate the change in the OPT3001 INT pin when light values are outside these values (1 marks)
	- For High Limit you can use the simplified equation from the documentation of M = Lux / (0.01 × 2^E) and I just used the max mantissa size (4095) to find the exponent:
		- E = log2(2500/(0.01×4095)) = log2(61.05) ≈ 6 
		- and doing that to find lux gives you a value of roughly 2600 lux