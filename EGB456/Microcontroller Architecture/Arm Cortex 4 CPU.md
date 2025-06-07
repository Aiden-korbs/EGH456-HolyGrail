*See [[Arm Cortex Types]] for summary*

[Arm Specs Website](https://developer.arm.com/Processors/Cortex-M4)

**Specifics:**
	- Architecture Name: Armv7E-M
	- 32 bit, 120Mhz Clock Speed
	- 150 Dhrystone million instructions per second (DMIPS)
		- Drhystone is a benchmark simulating computational tasks, mostly integer operands
	- Thumb-2 Mixed 16-/32-bit [[Instruction Set|instruction]] set
		- includes fixed 32-bit Arm [[Instruction Set|instruction]] set
		- Thumb instructions variable length 8/16-bit
		- Thumb-2 is an enhanced instruction set from ARM, blending 16-bit and 32-bit instructions to optimise both code density and performance
	- IEEE754-compliant single-precision Floating-Point Unit (FPU)
		- IEEE 754-compliant ensures that software and hardware perform floating-point calculations in a way that yields consistent results across different platforms
	- 16-bit Single Instruction Multiple Data (SIMD) vector processing unit
		- Can do parallel processing and Vectorisation improving compute time on large datasets
	- 3 Stage pipeline + Harvard architecture characterised by separate buses for instruction and data
		- Just GPT it when you get back here dude

**Cortex-M3 (&M4) has a 3 stage [[The Fetch-Decode-Execute Cycle|FDE Pipeline]]**
	- Does more in each stage to increase overall performance
	
![[Screenshot 2025-03-12 at 8.25.28 PM.png|400]]

**ARM Cortex-M3 (&M4) v7M Core, a Register-Register Machine**:
	Is also known as a load-store architecture
		1. Processor loads data from memory to internal registers
		2. After processing data will be written back to memory, only if required
		
		![[Screenshot 2025-03-12 at 8.40.45 PM.png|400]]

**Arm Cortex 4 Expanded Architecture:**
![[Screenshot 2025-03-13 at 3.25.06 PM.png|500]]