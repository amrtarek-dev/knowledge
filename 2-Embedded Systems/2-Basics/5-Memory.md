Memories in computer are electronics components that stores data and program instructions.

``` markdown
            +--------+                 __
           / Register \ 1 Cycle         |
          +------------+                | Primary
	     /    Caches    \ ~10           | Storage
        +----------------+              |
       /   Main Memory    \ ~100        |
      +--------------------+           __
	 /      Flash Disk      \ ~ 1M      |
    +------------------------+          | Secondary
   /     Traditional Disk     \ ~ 10M   | Storage
  +----------------------------+        |
 /   Remote Secondary Storage   \       |
+--------------------------------+     __

<------- Storage Capacity ------->

```

## Register
It is the fastest memory component, it reads and write in 1 CPU cycle because it is on the CPU, volatile memory.

## Caches
Its storage capacity is bigger than Register, but it is slower and it is on the CPU too, volatile memory.

## Main Memory (RAM)
Its storage capacity is bigger than Caches, but it is slower than Caches and it is not on the CPU, volatile memory.
Types:
- SRAM: Static RAM
	- It is larger (physical size), consume more power, and smaller in capacity than DRAM.
	- But it is faster
- DRAM: Dynamic RAM
	- it is smaller, and slower than SRAM.
	- But it has more capacity, consume less power.

## Flash Disk (ROM)
Its storage capacity is bigger than RAM but slower, and it is non-volatile
Types:
- MROM: Maskable ROM, and can not be programmed
- PROM: Programmable ROM, and can be programmed once.
- EPROM: Erasable PROM, it can be erased using UV and reprogrammed.
- EEPROM: Electrically EPROM, it can be electrically erase and reprogrammed.
- Flash: It is EEPROM with larger page size.

## Traditional Disk (HDD)
Its storage capacity is bigger than Flash disk but slower, and it is non-volatile.

## Remote Secondary Storage
Its storage capacity is bigger than Traditional disk, but slower, and depends on the network speed.