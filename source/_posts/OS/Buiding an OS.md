---
title: 构建一个操作系统
math: true
date: 2023-06-20 09:49:54
---

## Hello world

### How a computer statrts up

1. BIOS is copied from a ROM chip into RAM
2. BIOS starts executing code
   - initlializes hardware
   - runs some tests(POST=power-on self test)
3. BIOS searches for an operating system to start
4. BIOS loads and starts the operating system
5. Operating system runs

### Legacy booting

- BIOS loads first sector of each bootable device into memory(at location 0x7C00)
- BIOS checks for 0xAA55 signature
- If found, it starts executing code

### EFI

- BIOS looks into special EFI partitions
- Operating system must be compiled as an EFI program

### ORG(derective)

Tells assembler where we expect our code to be loaded. The assembler uses this information to calculate label addresses.

### Directive

- Gives a clue to the assembler that will affect how the program gets compiled. Not translated to machine code!
- Assember specific -- different assemblers might have different directiges.

### Instruction 

- Translated to a machine code instruction that the cpu will execute.

### BITS(directive)

Tell assembler to emit 16/32/64-bit code

### JMP location

Jumps to given location, unconditionally (equivalent with goto instruction in C).











