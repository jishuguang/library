# ELF

Executable and Linkable Format

## Layout and structure

Link view
- ELF header
- program header table (optional)
- section1...n
- section header table

Execution view
- ELF header
- program header table
- segment1...n
- section header table (optional)

readelf tool

### ELF header

readelf -h xxx

### Program header table

readelf -l xxx
type
- PHDR
- INTERP
- LOAD
- DYNAMIC
- NOTE

### Sections

readelf -S xxx
Name
- .text
- .rel.text
- .data
- .bss
- .rodata
- .symtab
- ...

### Symbol table

nm tool

### String table

.strtab
.shstrtab

## Data structure in kernel

elf.h

struct elf32/64_hdr (elf header)
struct elf32/64_phdr (program header)
struct elf32/64_shdr (section header)
struct elf32/64_sym
- st_info
  - Bind: STB_LOCAL/GLOBAL/WEAK
  - Type: STT_OBJECT/FUNC/NOTYPE

### Relocation entries

readelf -r xxx

struct elf32/64_rel/rela

relocation type
- PC-relative
- Absolute

### Dynamic linking

data for dynamic linker
- .dynsym: symbol table
- .dynamic: struct dynamic (readelf - dynamic xxx)
  - d_tag: DT_NEEDED/DT_STRTAB/DT_SYMTAB/DT_INIT/DT_FINT
  - d_un