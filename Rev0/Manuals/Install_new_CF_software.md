# Procedure for installing software on a new K80 CF disk
### Introduction
This is step-by-step procedure for installing software on a new CF disk for K80. The CF disk must be have a capacity of 32Meg or larger.

### Format the new CF disk
A new CF disk must be format to CP/M file system. **Caution: the formatting process will erase all files on the CF disk**. The formatting is done with the “xX” command of the K80 Monitor as follow: Power on the board or press reset to run the K80 monitor. At the '>' prompt, type:

*xA to format drive A*

*xB to format drive B*

*xC to format drive C*

*xD to format dirve D*

Please note the drive letter (A/B/C/D) must be in upper case.

### Installing CP/M 2.2 BDOS/CCP/BIOS
CP/M 2.2 BDOS/CCP/BIOS is installed in track 0 of the CF disk. At the K80 monitor prompt, load the Intel hex file 'cpm22all.hex'; after the file load is completed, type 'c2' to copy CP/M2.2 to track 0 of the CF disk. The command 'b2' will boot CP/M 2.2, but there are no files on the CF disk right now.

### Installing XMODEM on CF disk
XMODEM.COM will be the very first file on the new CF disk. At the K80 monitor prompt, load the Intel hex file 'xmodem.hex'; after the file load is completed, type 'b2' to boot up CP/M 2.2 and then type 'save 17 xmodem.com' at CP/M prompt. This will save the xmodem.hex that's in the memory as a executable CP/M file in CF disk.

### Loading software on CF disk
Once xmodem is installed, it is used to load all subsequent files into the CF disk. At the CP/M 2.2 prompt, type:

*xmodem unarj.com /r/z1*

This will first load a decompressing software, unarj.com, to the new CF disk. Then type at the CP/M 2.2 prompt:

*xmodem cpm2.arj /r/z1*

This will load the compressed CP/M 2.2 distribution files. After cpm2.arj is loaded, type at the CP/M 2.2 prompt:

*unarj e cpm2*

This will decompress the CP/M 2.2 distribution files. The CF disk is now ready for use.

**Video of creating a new CF disk**
[video](create_new_cf_disk_in_k80.mp4)
