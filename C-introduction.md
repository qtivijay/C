Table of contents
- [Microcontroller vs Microprocessor](#-1.Microcontroller-vs-Microprocessor)
- [Microcontroller vs SOC](#-2.Microcontroller-vs-SOC)
- [How do you develop software for Microcontroller](#-3.How-do-you-develop-software-for-Microcontroller)
- [Difference Between Compiler, Assembler, Linker, and Loader (C Program)](#-4.Difference-Between-Compiler,-Assembler,-Linker,-and-Loader) 
- [Difference Between Compilation Error and Runtime Error](#-5.-Difference-Between-Compilation-Error-and-Runtime-Error)


# 1.Microcontroller vs Microprocessor
### Microcontroller (MCU)
A **microcontroller** is a compact integrated circuit designed for **specific control tasks** in embedded systems. It includes:
- **CPU** (Central Processing Unit)
- **Memory** (RAM, ROM, Flash)
- **I/O peripherals** (Timers, ADC, GPIO, UART, SPI, I2C)

### **Microprocessor (MPU)**
A **microprocessor** is a standalone **CPU** that requires external components to function. It is used in **general-purpose computing** and lacks built-in memory or peripherals.

### **Key Differences**
| Feature | Microcontroller (MCU) | Microprocessor (MPU) |
|---------|----------------------|----------------------|
| **Integration** | CPU, memory, and peripherals on a single chip | Only CPU, requires external memory and peripherals |
| **Application** | Embedded systems (IoT, automotive, appliances) | General-purpose computing (PCs, servers) |
| **Power Consumption** | Low power, optimized for efficiency | Higher power, requires cooling solutions |
| **Operating System** | Typically runs **bare-metal code** or **RTOS** | Runs **full OS** like Linux, Windows |
| **Cost** | Lower cost due to integration | Higher cost due to external components |
| **Performance** | Optimized for real-time control | High-speed processing for complex tasks |

### **Examples**
- **Microcontrollers**: STM32, PIC, ATmega, ESP32
- **Microprocessors**: Intel Core i7, AMD Ryzen, ARM Cortex-A

---

# 2.Microcontroller vs SOC
### **Microcontroller (MCU)**
A **microcontroller** is a **single-chip solution** with a processor, memory, and basic peripherals designed for **specific control applications**.

### **System-on-Chip (SoC)**
A **SoC** integrates **multiple processing units (CPU, GPU, DSP), extensive memory, and specialized peripherals** into a single chip. It is used in **smartphones, routers, and high-end embedded systems**.

### **Key Differences**
| Feature | Microcontroller (MCU) | System-on-Chip (SoC) |
|---------|----------------------|----------------------|
| **Integration** | CPU, memory, and basic peripherals | CPU, GPU, DSP, memory, and advanced peripherals |
| **Application** | Simple embedded tasks (sensor control, automation) | Complex computing (smartphones, AI, networking) |
| **Power Consumption** | Low power, optimized for efficiency | Higher power, varies by application |
| **Operating System** | Runs **bare-metal code** or **RTOS** | Runs **full OS** like Linux, Android, Windows |
| **Performance** | Limited processing power | High-performance computing with multiple cores |
| **Cost** | Lower cost due to simplicity | Higher cost due to advanced features |

### **Examples**
- **Microcontrollers**: STM32, ATmega, ESP32
- **SoCs**: Qualcomm Snapdragon, Apple M-Series, NVIDIA Jetson, Raspberry Pi Broadcom SoCs

# 3.How do you develop software for Microcontroller

- Keil IDE : Integrated Development Environment
  -  collection of tools like text editor, compiler , linker, debugger.
- C programs  - H/W doesn't understand C statements
  -  (Highlevel level language )convert the c code to machine understandable language (low level language)
  -  .c --> .s (assembly code file) --> .o (object code file).
  -  compiler which converts highlevel language to low level language.
- Software development done in host development PC and generate binaries / executables / images.
- These binaries will be loaded in Target H/W Platform

# 4.Difference Between Compiler, Assembler, Linker, and Loader

## 1. Compiler
- Translates **C source code** into **assembly language**.
- Checks for syntax errors and optimizes the code.
- Example: Converts `printf("Hello, World!");` into assembly instructions.

## 2. Assembler
- Converts **assembly code** into **machine code** (binary format).
- Produces an **object file** (`.o` or `.obj`).
- Example: Converts assembly instructions into binary instructions that the CPU understands.

## 3. Linker
- Combines multiple **object files** and **library files** into a single **executable file** (`.exe` or `.out`).
- Resolves function calls (e.g., linking `printf()` from the standard library).
- Example: If your program uses multiple `.o` files, the linker merges them into one executable.

## 4. Loader
- Loads the **executable file** into memory for execution.
- Allocates memory and sets up the program's runtime environment.
- Example: When you run `./a.out`, the loader places the program in memory and starts execution.


# 5. Difference Between Compilation Error and Runtime Error

## **Key Differences**

| Feature            | Compilation Error | Runtime Error |
|--------------------|------------------|--------------|
| **When it occurs** | During compilation | During program execution |
| **Cause** | Syntax errors, type mismatches, missing declarations | Invalid operations like division by zero, accessing invalid memory |
| **Detection** | Identified by the compiler before execution | Occurs while the program is running |
| **Examples** | Missing semicolon, undeclared variable, incorrect function call | Division by zero, accessing an array out of bounds, null pointer dereference |
| **Fixing** | Must be corrected before running the program | Requires debugging after execution |



