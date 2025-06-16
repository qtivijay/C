Table of contents
- [Microcontroller vs Microprocessor](#-1.Microcontroller-vs-Microprocessor)
- [Microcontroller vs SOC](#-2.Microcontroller-vs-SOC)
- [How do you develop software for Microcontroller](#-3.How-do-you-develop-software-for-Microcontroller)
- [Difference Between Compiler, Assembler, Linker, and Loader (C Program)](#-4.Difference-Between-Compiler,-Assembler,-Linker,-and-Loader) 
- [Difference Between Compilation Error and Runtime Error](#-5.-Difference-Between-Compilation-Error-and-Runtime-Error)
- [Relationship Between C Code, Assembly Language, Opcode, and Operand](#-6.Relationship-Between-C-Code,-Assembly-Language,-Opcode,-and-Operand)
- [vi Editor Cheat Sheet](#-7.vi-Editor-Cheat-Sheet)

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

# Opcode and Operand in C Programming

## 1. **Opcode and Operand**
In **C programming**, while we don’t directly interact with **opcodes and operands**, they are fundamental concepts in assembly language and machine-level programming.

## 2. **Definitions**
- **Opcode (Operation Code)**: Specifies the operation to be performed by the processor. Example: `ADD`, `MOV`, `SUB`.
- **Operand**: Represents the **data** or **memory location** on which the operation is performed.

## 3. **Example**
Assembly instruction:
```assembly
ADD R1, R2
```

# 6.Relationship Between C Code, Assembly Language, Opcode, and Operand

## 1. **Overview**
- **C programming** is a high-level language that allows structured and readable code.
- **Assembly language** provides a low-level representation of CPU instructions.
- **Opcodes and operands** are core components of machine code.

## 2. **Translation Process**
### **C Code → Assembly Language → Machine Code**
1. **C Code** is compiled into **assembly language** by a compiler.
2. **Assembly code** is translated into **machine code** by an assembler.
3. **Machine code** consists of **opcodes** (instructions) and **operands** (data/memory locations).

### Example:
c code:
```c
#include <stdio.h>
int main() {
    int a = 5, b = 10;
    int sum = a + b;
    printf("Sum: %d\n", sum);
    return 0;
}
```
assembly code:
```assembly
MOV R0, #5    ; Load value 5 into Register R0
MOV R1, #10   ; Load value 10 into Register R1
ADD R2, R0, R1 ; Add R0 and R1, store result in R2
```
opcodes and operands:
```opcode
E3A00005  ; MOV R0, #5
E3A0100A  ; MOV R1, #10
E0802001  ; ADD R2, R0, R1
```

### Execution Flow
1. Write code on the development machine.
2. Compile using a compiler to generate object files.
3. The linker merges them into an executable.
4. The loader transfers the executable to the target board, where it runs.

```
Kiel IDE which has text editor , compiler , linker/loader , debugger which is used for
software development of Microcontroller and not for SOC
```
# 7.vi Editor Cheat Sheet

## Introduction
The `vi` editor is a powerful text editor available on Unix-based systems. It operates in **two primary modes**:
1. **Command Mode** – Used for administrative tasks like saving, exiting, cutting, copying, pasting, replacing, and searching.
2. **Insert Mode** – Used for writing and editing text.

By default, the `vi` editor opens in **Command Mode**.

---

## Opening a File
To open or create a file using `vi`, use the following command:
```sh
vi filename
```
If the file exists, it will open in **Command Mode**.

---

## Switching Between Modes
- **Command Mode → Insert Mode**  
  Press one of the following keys:
  - `i` (insert at cursor)
  - `a` (append after cursor)
  - `o` (open a new line below)
  - `O` (open a new line above)

- **Insert Mode → Command Mode**  
  Press the `ESC` key.

---

## Basic Operations
### Exiting `vi`
| Command       | Description                |
|--------------|----------------------------|
| `:q`         | Quit without saving        |
| `:q!`        | Quit and discard changes   |
| `:wq` or `ZZ` | Save and exit              |

### Saving Changes
| Command | Description |
|---------|-------------|
| `:w`    | Save file   |

**Note:** Save operations cannot be performed in **Insert Mode**. Press `ESC` first to return to **Command Mode** before saving.

---

## Editing Text
### Inserting and Appending
| Command | Description |
|---------|-------------|
| `i`     | Insert text at cursor |
| `I`     | Insert at the beginning of the line |
| `a`     | Append after cursor |
| `A`     | Append at the end of the line |
| `o`     | Open a new line below |
| `O`     | Open a new line above |

### Deleting and Copying
| Command | Description |
|---------|-------------|
| `x`     | Delete character under cursor |
| `dw`    | Delete a word |
| `dd`    | Delete the current line |
| `yy`    | Copy the current line |
| `p`     | Paste copied/deleted content |

---

## Searching and Navigation
| Command | Description |
|---------|-------------|
| `/pattern`  | Search forward for "pattern" |
| `?pattern`  | Search backward for "pattern" |
| `n`         | Repeat search in same direction |
| `N`         | Repeat search in opposite direction |
| `G`         | Jump to the last line |
| `gg`        | Jump to the first line |
| `Ctrl + f`  | Scroll forward one screen |
| `Ctrl + b`  | Scroll backward one screen |

---

## Undo and Redo
| Command | Description |
|---------|-------------|
| `u`     | Undo last change |
| `Ctrl + r` | Redo undone change |

---

## Miscellaneous Commands
| Command | Description |
|---------|-------------|
| `:set number` | Show line numbers |
| `:set nonumber` | Hide line numbers |
| `:%s/old/new/g` | Replace "old" with "new" in the entire file |

---

## Summary
The `vi` editor is a versatile tool widely used for editing files in Linux environments. Mastering its modes and commands enhances productivity, making it an essential skill for developers and system administrators.



