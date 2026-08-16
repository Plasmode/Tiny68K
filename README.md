# Tiny68K
Tiny68K is a high-performance yet low-cost single board computer based on the Motorola 68000.
![Tiny68K_rev2](tiny68k_rev2_topview.jpg)

### Features
- Motorola 68000 CPU
- MC68681 DUART, port A is the console operating at 38400 baud, 8N1, with CTS/RTS hardware handshake.
- Altera EPM7128 CPLD contains the glue logics:
  -  State machine to load 32K serial flash when powered up or with a reset,
  -  DRAM controller for a 16-megabyte SIMM72 DRAM module,
  -  Hidden CAS-before-RAS refresh in hardware, no software overhead required,
  -  memory decoder,
  -  Interrupt controller,
  -  Bus Error watchdog timer,
- 8-16 MHz 0scillator (only 8 MHz operation is tested)
- 32Kbyte serial flash, 24C256 as the boot device.
- Second 32K serial flash that can be programmed in situ and serves as the boot device with just one jumper change.
- 44-pin edge connector interfaces to a low-cost IDE-CF module
- SIMM72 socket to accommodate a 16-megabyte SIMM DRAM module
- SIMM72 expansion port (currently not tested)
- 7-segment LED display as visual indicator of board operations.
- Target for CP/M-68K ver 1.3
- 100mm x 100mm 2-layer pc board
- 5V operation


Tiny68K has two unusual features:

- The entire 16-megabyte memory space of 68000 (except the top 32Kbyte of I/O space) is filled with RAM,
- The boot software residesin a 32Kbyte serial flash that is copied into the lowest 32Kbyte of the DRAM when powered up or with a reset. The RAM-resident boot software can be modified just like any data in RAM but is overwritten on the next power cycle or with a reset.
