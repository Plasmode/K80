# K80W Rev1, A RomWBW-capable Z80 SBC
### Introduction
**Note, K80W rev1 is superceded by [K80W rev2.1](../K80W_Rev2)**

K80W is similar to K80. It is a 22MHz Z80 SBC with KIO (Z84C90) as the I/O device. It is designed to run RomWBW

www.retrobrewcomputers.org_lib_plugins_ckgedit_fckeditor_userfiles_image_builderpages_plasmo_k80_k80w_rev1_annotated.jpg

## Features
- Z80 overclocked to 22MHz,
- 512KB Flash divided into 16 32KB banks,
- 512KB RAM divided into 16 32KB banks,
- KIO, Z84C90, is the integrated I/O interface,
- DS1302 Real Time Clock,
- Compact Flash interface,
- Designed for RomWBW
- Two 40-pin RC2014-compatible expansion slots,
- 100mm X 100mm, 2-layer PC board,
## Design Files
- Schematic
- Gerber photoplots
- CPLD design files
- Bill of Materials

## Software
### Adding SD to K80W
www.retrobrewcomputers.org_lib_plugins_ckgedit_fckeditor_userfiles_image_builderpages_plasmo_k80_k80wwithsd.jpg

  - PB0 to MOSI,
  - PB7 to MISO,
  - PB3 to CS and
  - PB4 to CLK
### RomWBW Configuration
The following modifications to RCZ80_K80W.ASM file is needed:

SDENABLE .SET TRUE ; SD: ENABLE SD CARD DISK DRIVER (SD.ASM)
SDMODE .SET SDMODE_PIO ; SD: DRIVER MODE: SDMODE_[JUHA|N8|CSIO|PPI|UART|DSD|MK4|SC|MT|PIO|Z80R|USR]


This is the resulting RCZ80_K80W.ASM

The I/O addresses for SDMODE_PIO is hardwired to $69. It is necessary to modify SD.ASM in HBIOS as follow:

SD_IOBASE .EQU $82 ; IO BASE ADDRESS FOR SD INTERFACE

SD_DDR .EQU $83 ; DATA DIRECTION REGISTER

This is the resulting ROM binary file that recognizes SD card connected to PIO:
