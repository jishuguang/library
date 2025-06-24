# Boot

## Overview

boot phase
- kernel loading
- platform-dependent initialization
- platform-indepdent initialization

## Arch-specific setup

IA-32
- boot/compressed/head_32.S -> startup_32
- kernel/head_32.S -> startup_32

## High level initialization

start_kernel
- mm setup (setup_arch)
  - setup_memory
  - paging_init
- cmd args (parse_args)
  - struct kernel_param
- core data struct of subsys
  - xxx_init
- determine error (check_bugs)
- idle process and init thread
  - rest_init
    - kernel_init
      - smp initialization
      - do_basic_setup
        - init_workqueues
        - driver_init
        - do_initcalls
      - prepare namespace
      - free_initmem
      - init_post
        - userspace initialization /sbin/init
        - kernel_execve
    - kthreadd
    - cpu_idle