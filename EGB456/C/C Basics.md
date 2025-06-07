### C Versions
• ANSI C or C89 did not specify the sizes and ranges of integer data types
• It allowed different representations of integers (sign magnitude, 1s complement and 2s complement.
• C99 (introduced in 1999) introduced new types and fixed the ranges and sizes. These are specified in stdint.h

### Integer Types
• unsigned, signed, short, and long are modifiers 
• If one or more modifier is used, int is assumed and may be omitted. 
• If neither signed or unsigned is used, signed is assumed and may be omitted. 
• int with no modifier is a data type whose size varies among compilers.

##### Recommended Data Types

| Size    | Signed  | Unsigned |
| ------- | ------- | -------- |
| 8 bits  | int8_t  | uint8_t  |
| 16 bits | int16_t | uint16_t |
| 32-bits | int32_t | uint32_t |
| 64-bits | int64_t | uint64_t |

### Values defined in limits.h
Most compilers provide a standard file limits.h specifying the following:

| Data Type              | Minimum   | Maximum    |
| ---------------------- | --------- | ---------- |
| signed char            | SCHAR_MIN | SCHAR_MAX  |
| signed short int       | SHRT_MIN  | SHRT_MAX   |
| signed long int        | LONG_MIN  | LONG_MAX   |
| signed long long int   | LLONG_MIN | LLONG_MAX  |
| unsigned char          | 0         | UCHAR_MAX  |
| unsigned short int     | 0         | USHRT_MAX  |
| unsigned long int      | 0         | ULONG_MAX  |
| unsigned long long int | 0         | ULLONG_MAX |
#### Contents of limits.h
	#define SCHAR_MIN -127
	#define SCHAR_MAX 127
	#define SHRT_MIN -32767 (not -32768) 
	#define SHRT_MAX 32767 
	#define INT_MIN -2147483647 (**) 
	#define INT_MAX 2147483647 
	#define LONG_MIN -2147483647 (**) 
	#define LONG_MAX 2147483647

### C99 Header File stdbool.h
##### C99 introduced these boolean data types
	#define bool _Bool
	#define false ((_Bool) 0) 
	#define true ((_Bool) 1)
##### Alternative definitions
	#define bool unsigned char // macros 
	#define false 0 
	#define true 1 
	typedef unsigned char bool ; // unsigned char’s 
	const unsigned char false = 0 ; 
	const unsigned char true = 1 ; 
	typedef enum {false = 0, true = 1} bool; // enumerated type

