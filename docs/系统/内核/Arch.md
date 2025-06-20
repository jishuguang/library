# Arch

## Overview

include/asm -> include/asr-arch
arch/arch

## Data types

Elementary data types
- standard data types
- fixed-bits number (asm-arch/types.h)
  - u32
  - s16
  - ...
- subsystem-specific types
  - pid_t
  - ...

## Alignment

non-aligned access (asm-arch/unaligned.h)
- get_unaligned
- put_unaligned

## Memory pages

Memory page (asm-arch/page.h)
- size: PAGE_SHIFT/SIZE/ALIGN
- operation
  - clear_page
  - copy_page

## System call

asm-arch/unistd.h
- symbolic constants
  - __NR_chdir
  - ...

## String processing

asm-arch/string.h
- for string
  - strcmp
  - str...
- for general memory
  - memset
  - mem...

## Thread representation

asm-arch/ptrace.h
- pt_regs

asm-arch/processor.h
- struct thread_struct

asm-arch/thread.h
- struct thread_info

## Bit operations and endianness

asm-arch/bitops.h
- set_bit
- ...

asm-arch/byteorder.h
- __cpu_to_le64
- ...

## Page tables

asm-arch/pgtable.h

## Misc

### Checksum

asm-arch/checksum.h

### Context switch

asm-arch/system.h
- switch_to

### Current process

asm-arch/current.h