#### Summary:

Linker scripts define how program sections are mapped into memory on an embedded system. They are essential for specifying memory regions and placement of segments like `.text`, `.data`, and `.bss`.

---

### 📜 Linker Scripts

**Slide 19 Overview:**

- **Memory blocks** must be explicitly defined:
    

```ld
MEMORY {
  FLASH (rx)  : ORIGIN = 0x00000000, LENGTH = 0x00100000
  SRAM  (rwx) : ORIGIN = 0x20000000, LENGTH = 0x00040000
}
```

- **Section Mapping** specifies how to place code and data:
    

```ld
SECTIONS {
  .text : { *(.text) } > FLASH
  .data : { *(.data) } > SRAM
  .bss  : { *(.bss)  } > SRAM
}
```

---

### 🗂️ Components of a Linker Script

- **MEMORY block**:
    
    - Describes memory regions available in the system.
        
    - Each region has a name, origin address, size, and attributes.
        
- **SECTIONS block**:
    
    - Maps sections from input object files to physical memory locations.
        
    - Specifies which data/code goes to which memory region.
        

---

### 🛠️ Usage in Projects

- Linker scripts are essential for correct memory layout in embedded systems.
    
- Usually provided by vendor or toolchain (e.g., `startup_gcc.c`, `.ld` files in TI examples).
    
- Can be customized to reserve regions for peripherals, bootloaders, etc.
    

---

### 🧪 Debugging Tips

- Use `--Map=output.map` build flag to inspect where each section ends up in memory.
    
- Mismatches or overflows usually mean your `.bss` or `.stack` section is too large.
    

**Diagram Reference:**

- Slide 20: Linker memory allocation and segment mapping table
    

---

### 🔗 See Also

- [[Build Process]]
    
- [[Object File Format]]