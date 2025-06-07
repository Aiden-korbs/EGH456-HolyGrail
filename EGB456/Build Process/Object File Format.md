
Object files are the intermediate output of compilation and assembly. They follow the ELF (Executable and Linkable Format) and organize code/data into sections. These sections are processed during linking and relocation to create the final binary.

---

### 📦 Object File Format

**Slide 12–14 Overview:**

- Object files are either:
    
    - **Relocatable** (`.o`)
        
    - **Executable** (`.elf`)
        
    - **Shared** (`.so`, for shared libraries)
        
- **Formats**:
    
    - **COFF** (older format)
        
    - **ELF** (modern standard)
        

**ELF File Layout:**

- **ELF Header**: File metadata
    
- **Section Header Table**: Maps out all sections
    
- **Program Header Table**: Organizes sections into segments for memory mapping
    
- **Sections** (individual code/data blocks):
    
    - `.text` – executable code
        
    - `.data` – initialized global/static vars
        
    - `.bss` – uninitialized globals
        
    - `.rodata` – read-only constants (e.g., strings)
        
    - `.symtab` – symbol table for functions and variables
        

**Diagram Reference:**

- Slide 13–14: Block diagram showing section and segment layout
    

---

### 📑 Sections Overview

|Section|Initialized|Notes|
|---|---|---|
|`.text`|Yes|Executable code, typically read-only|
|`.data`|Yes|Initialized global/static variables, read-write|
|`.bss`|No|Uninitialized global/static vars, zeroed at start|
|`.rodata`|Yes|Constants and literals, read-only|
|`.stack`|No|System stack space|
|`.heap`|No|Heap space for dynamic memory|
|`.symtab`|-|Debug and linker info on functions/variables|
|`.cio`|No|Std I/O buffering|
|`.init_array`|Yes|C++ constructor function pointers|

---

### 🧠 Key Ideas

- Sections are **logical divisions** used by compilers.
    
- Segments are **memory-mapped groupings** of sections.
    
- Linker scripts and locators map sections to physical memory.
    
- `.bss` takes no space in file; zeroed at runtime.
    

---

### 🔗 See Also

- [[Build Process]]
    
- [[Linker Scripts]]