### Boolean and Bitwise Operators
Bitwise operators are used to manipulate bits.

| Operation | Boolean Operator | Bitwise Operator |
| --------- | ---------------- | ---------------- |
| AND       | &&               | &                |
| OR        | \|\|             | \|               |
| XOR       | unsupported      | ^                |
| NOT       | !                | ~                |

### Boolean Values
-
	Boolean operators yield results of type int, with true and false represented by 1 and 0. 
	Any numeric data type may be used as a Boolean operand. 
	Zero is interpreted as false; any non-zero value is interpreted as true.

### Manipulating Bits
Example UARTCTL Register:

	![[Screenshot 2025-03-13 at 8.02.15 PM.png]]
	Usage: Set or clear bits to control behavior of UART device

**Testing Bits:**

A constant mask such as 0x40 could be used.
a constant-valued shift expression provides a clearer indication of the bit position being tested: 
```c
if (bits & (1 << 6)) /* check to see if bit 6 is set */
```
Most compilers will replace such expressions by a single constant and there is no overhead of additional code.

##### Setting Bits
Setting a bit to 1 with the bitwise-OR operator:
```c
bits = bits | (1 << 6) ; /* sets bit 6 */
```
![[Screenshot 2025-03-13 at 8.07.54 PM.png|350]]
written more succinctly as:
```c
bits |= (1 << 6) ; /* sets bit 6 */
```

##### Clearing and Inverting Bits
Clearing bit 7 in variable data to 0 with the bitwise-AND operator:
```c
data &= ~(1 << 7) ; /* clears bit 7 */
```
(1 << 7)   -->   10000000 
~(1 << 7)  -->   01111111

Inverting a bit (toggling) with the bitwise-XOR operator as in:
```c
data ^= (1 << 6) ; /* flips bit 6 */
```
where bit 6 of data is toggled.

##### Extracting Bits:
Example: 0x3F = 0011 1111

**Process:**
![[Screenshot 2025-03-13 at 8.19.18 PM.png|400]]

##### Inserting Bits 
Example: Insert new_mins = 100011

Process:
![[Screenshot 2025-03-13 at 8.20.15 PM.png|410]]