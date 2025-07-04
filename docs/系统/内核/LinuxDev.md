# Linux dev

## Kernel source organization

root
- kernel
- mm
- init
- sound
- fs
- net
- lib
- drivers
- include
- crypto
- security
- Documentation
- arch
- scripts

## Configuration with Kconfig

### Kconfig

Menus
- menu/endmenu
- menuconfig

Configuration options
- config
  - type
    - tristate: y/n/m
    - bool
    - string
    - hex
    - integer
- choice/endchoice

Attributes
- depends on
- default
- range
- select
- help/--help
- all these attributes may also be followed by an if

Dependencies
- =/!=
- !/&&/||

### Processing config

make
- menuconfig
- oldconfig
- defconfig
- allyesconfig/allmodconfig/allnocofig

user-defined configuration options
- .config/config.h/autoconf.h

## Kbuild

make help

Makefile structure
- main Makefile
  - local tool
  - kernel tool
- arch/arch/Makefile
- scripts/Makefile.*
- subdir containing Makefiles
  - obj-y = xxx.o
  - obj-$(XX) += xx.o
  - obj-m += xx.o

## Debugging

- GDB/DDD
- /proc/kcore (current state of the kernel in ELF core format)
- KGDB

## User-Mode Linux

ARCH=um