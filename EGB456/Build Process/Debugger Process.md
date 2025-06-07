#### Summary:

Debugging the embedded system build process involves verifying syntax, memory layout, and runtime behaviour. Tools include map files, debuggers, and proper compiler/linker flags.

---

### 🐞 Debugging Process

**Slide 25–26 Overview:**

- **Build and Run Sequence:**
    
    1. Edit and compile source code
        
    2. Fix syntax/compiler errors
        
    3. Build full binary
        
    4. Flash and test on hardware
        
- **Common Debugging Tools:**
    
    - Compiler warnings and errors (`-Wall`, `-Wextra`)
        
    - Map files (`--Map=output.map`) to verify memory allocation
        
    - GDB or IDE debugger: step through, set breakpoints, watch variables
        

---

### 🛠️ Debugging Tips

- Avoid relying solely on `printf` for debugging (inefficient and slow)
    
- Use:
    
    - Breakpoints to isolate errors
        
    - Variable watches to track program state
        
    - Stack trace to identify crashes
        
    - Register view to validate low-level hardware control
        
    - Comment out code to isolate specific segments
        

---

### 🧪 Linker Map File

- Use build flag: `--Map=output.map`
    
- Includes:
    
    - Memory regions (origin, length, usage)
        
    - Segment allocation (e.g., `.intvecs`, `.text`, `.bss`)
        
    - Symbol allocation and object file contributions
        

**Example Output:** (Slide 20)

```
FLASH     0x00000000   1MB   used: 65kB
SRAM      0x20000000 256kB   used: 0.6kB
```

---

### 🔍 Common Errors

|Issue|Likely Cause|
|---|---|
|Stack overflow|Infinite recursion, large local variables|
|Memory corruption|Buffer overflow or bad pointer access|
|Unused sections|Linker script missing section mapping|
|Incorrect ISR behavior|ISR not mapped in vector table|

---

### 🔗 See Also

- [[Build Process]]
    
- [[Linker Scripts]]