# C In Kernel

## GUN C Compiler in kernel

Source to machine program:
- preprocessing
- scanning and parsing
- intermediate code generation
  - RTL
- Optimization
  - constant simplication
  - loop optimization
  - common subexpression elimination
  - dead code elimination
  - inline function
- Code generation
- assembler and linker

machine description
- instruction pattern

Procedure calls
- frame pointer
- return address
- old frame pointer
- local variable
- params
- stack pointer

Attributes
- __attribute__((xxx))
- noreturn
- regparam
- section
- align

inline assembler
- asm ("code;": output operand spec: input operand spec: modified regs);
- operand spec: "constraint" (variable)
  - r: reg
  - m: memory
  - I/J: constant
  - modifier
    - =: ro
    - +: ro

__builtin funcction
- __builtin_return_address
- __builtin_expect
  - likely
  - unlikely

pointer arithmetic

## Standard data structures and tricks

Reference counter
- struct shared
  - atomic_t count

Pointer type conversion

Alignment issues
- natural alignment
- generic alignment

Bit arithmetic

pre-processor tricks
- stringification
- concatenation

Misc
- do {} while(0)

Doubly linked list
- struct list_head
- list_add
- list_del
- list_for_each_entry
  - list_entry
    - container_of
      - offsetof

Hash lists
- struct hlist_head
- struct hlist_node

Red-Black tree
- struct rb_node

Radix tree
- struct radix_tree_node
- struct radix_tree_root