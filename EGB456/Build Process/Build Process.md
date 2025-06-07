#### Summary:

- The embedded systems build process includes:
    - Preprocessing (macros, header includes)
    - Compilation (C/C++ to assembly)
    - Assembly (assembly to machine code object files)
    - Linking (merging object files into a relocatable file)
    - Relocation (assigning physical memory addresses and producing the final binary image)
- Object files follow ELF format, segmented into sections like `.text`, `.data`, `.bss`, etc.
- Multithreading concepts include threads, ISRs, context switching, and critical sections.
- Figures from slides illustrate segment layouts and context switching mechanisms (e.g., Slide 17 for ELF/Segment breakdown, Slide 35 for context switching diagram).

---

### 🏗️ Build Process

**Slide 4–7:**

1. **Preprocessing**
    
    - `#include`, `#define`, conditional macros are resolved.
        
    - Header files are copied into source files.
        
2. **Compilation**
    
    - Converts C/C++ into assembly via parser, syntax analyser, optimizer, and code generator.
        
3. **Assembly**
    
    - Converts assembly into machine code (object files, `.o`).
        
4. **Linking** (Slide 15)
    
    - Merges object files.
        
    - Resolves external symbols.
        
    - Produces relocatable ELF file.
        
5. **Relocation** (Slide 16)
    
    - Assigns absolute addresses in memory.
        
    - Final binary image (`.bin`) ready to flash to microcontroller.
        

---
#### Summary:

The build process in embedded systems involves transforming high-level code into a machine-executable binary. It includes preprocessing, compiling, assembling, linking, and relocating code into the microcontroller’s memory.

---

### 🏗️ Build Process

**Slide 4–7 Overview:**

1. **Preprocessing**
    
    - Handles `#include`, `#define`, `#ifdef`, etc.
        
    - Copies included headers into the source file.
        
    - Resolves macros before compilation.
        
2. **Compilation**
    
    - Converts preprocessed C/C++ into assembly.
        
    - Utilizes parser, lexical analyzer, syntax analyzer, optimizer, and code generator.
        
    - Outputs assembly code for the assembler.
        
3. **Assembly**
    
    - Assembler turns assembly code into relocatable machine code object files (`.o`).
        
4. **Linking** (Slide 15)
    
    - Combines multiple object files.
        
    - Resolves symbols and dependencies.
        
    - Produces a single relocatable file (`.elf`).
        
    - Linker scripts (`.ld`) are used to control layout (Slide 19).
        
5. **Relocation** (Slide 16)
    
    - Assigns physical memory addresses.
        
    - Converts relative addresses in `.elf` to absolute addresses.
        
    - Produces the final binary image (`.bin`).
        

**Diagram Reference:**

- Slide 4: Build process flowchart
    
- Slide 17: ELF header, sections, and segment relationships
    

---

### 🧰 Tools Mentioned

- **GCC**: GNU Compiler Collection
    
- **PlatformIO**: Build system and project manager
    
- **Makefile/CMake**: Tools to define and automate the build process
    

---

### 🔍 Tips for Effective Builds

- Set proper optimization flags: `-O0`, `-O2`, `-O3`
    
- Use debug flags like `-g`, `-ggdb3`
    
- Watch out for memory alignment and section overflow
    
- Check linker map output (`--Map=output.map`) for debugging memory layout
    

---

### 📎 Related Files

- Linker scripts: Define memory regions and how to map sections
    
- Startup files: Initialize the interrupt vector and define default handlers
    
- Object files: Contain intermediate machine code before final binary
    

---

### 🔗 See Also

- [[Object File Format]]]
    
- [[Linker Scripts]]
    
- [[Debugger Process]]```ld
MEMORY {
  FLASH (rx)  : ORIGIN = 0x00000000, LENGTH = 0x00100000
  SRAM  (rwx) : ORIGIN = 0x20000000, LENGTH = 0x00040000
}

SECTIONS {
  .text : { *(.text) } > FLASH
  .data : { *(.data) } > SRAM
  .bss  : { *(.bss)  } > SRAM
}

- Defines memory layout of the microcontroller
    
- Maps program segments to appropriate regions
    

---

### 🐞 Debugging Build Process

**Slide 25–26:**

- **Avoid** `printf` debugging; use:
    
    - Breakpoints
        
    - Variable watches
        
    - Stack inspection
        
    - Register view
        
- Use linker map output with:
    
    - `--Map=output.map`
        
    - View layout and memory utilization (see Slide 20)
        

---

### 🧵 Multithreading

**Slide 27–37:**

- **Programming Model 1** – Single thread polling (Slide 28)
    
- **Model 2** – ISR-based, blocking ISRs risky (Slide 29)
    
- **Model 3** – RTOS with threads & ISR queues (Slide 30–31)
    

**Threads** (Slide 32):

- Contain init + infinite loop
    
- Wait for condition/event
    
- Reduced program complexity by separation
    

**Preemption** (Slide 33):

- A thread can be suspended by another (higher priority)
    

**Context Switching** (Slide 34–35):

- Save registers, PC, SP of current thread
    
- Restore values of next thread
    
- See diagram: _Thread A/B switching stacks and registers_
    

**Shared Resources** (Slide 36):

- Buffers, UART, global vars
    
- Uncoordinated access causes corruption
    

**Critical Sections** (Slide 37):

- Protect shared access with mutexes/semaphores
    
- Prevents interleaved prints:
    

```c
// Without protection:
printf("HELLO\n");
printf("goodbye");
// Can result in:
// HgoELodLO\nbye
```

---

### 🖼️ References to Figures:

- **Slide 17** – ELF and segment mapping
    
- **Slide 20** – Linker memory allocation map
    
- **Slide 30** – Multithreaded ISR queue diagram
    
- **Slide 35** – Context switching diagram (register + stack visuals)
    
- **Slide 37** – Interleaved output example with printf
    

[[EGB456]]