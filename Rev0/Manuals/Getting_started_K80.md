# Getting Started with K80
This is a quick start guide to get K80 power up and running

![annotated](../k80_rev0_topview_annotated.jpg)

Setup hardware
Refer to above picture for various functions.

K80 needs 5V@200mA via the 2.1mm X 5.5mm power jack
The 6-pin CP2102 USB-serial adapter can plug directly into the serial connectors labelled as “channel A” and “channel B”
The Z80 CPU clock is independent from the serial clock. The clock can be as low as 7.37MHz or as high as 24MHz.
Be sure the jumpers T43 and T44 are configured as shown in the picture.
Set the serial port terminal to 115200-N-8-1, no handshake.
builderpages/plasmo/k80/k8
