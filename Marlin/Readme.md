# Marlin for the Makerspace Wanhao i3 printer.

Based on https://www.thingiverse.com/thing:2450111 using the 10k resistor version which is correct for our board.

Updated to invert the z-axis direction because it was wrong for us.

# Flashing

The Meltzi board has a bootloader so you can flash directly from the Arudino IDE over USB (no programmer required)

Set your Arduino Sketch folder to this folder.  This will ensure that the graphics library is included and also that the Sanguino boards are available (in the hardware directory)

Select board type ATMega1284P (16Mhz)

# Other files

The file MeltziStockFirmware.hex is an extract of the original firmware from the Meltzi board

# Avrdude Commands

For future reference, should it be useful.

## Read device signature

```
"C:\Program Files (x86)\Arduino\hardware\tools\avr/bin/avrdude" -C"C:\Program Files (x86)\Arduino\hardware\tools\avr/etc/avrdude.conf" -v -patmega1284p -cstk500 -PCOM11

avrdude: Version 6.3, compiled on Jan 17 2017 at 12:00:53
         Copyright (c) 2000-2005 Brian Dean, http://www.bdmicro.com/
         Copyright (c) 2007-2014 Joerg Wunsch

         System wide configuration file is "C:\Program Files (x86)\Arduino\hardware\tools\avr/etc/avrdude.conf"

         Using Port                    : COM11
         Using Programmer              : stk500
         AVR Part                      : ATmega1284P
         Chip Erase delay              : 55000 us
         PAGEL                         : PD7
         BS2                           : PA0
         RESET disposition             : dedicated
         RETRY pulse                   : SCK
         serial program mode           : yes
         parallel program mode         : yes
         Timeout                       : 200
         StabDelay                     : 100
         CmdexeDelay                   : 25
         SyncLoops                     : 32
         ByteDelay                     : 0
         PollIndex                     : 3
         PollValue                     : 0x53
         Memory Detail                 :

                                  Block Poll               Page                       Polled
           Memory Type Mode Delay Size  Indx Paged  Size   Size #Pages MinW  MaxW   ReadBack
           ----------- ---- ----- ----- ---- ------ ------ ---- ------ ----- ----- ---------
           eeprom        65    10   128    0 no       4096    8      0  9000  9000 0xff 0xff
           flash         65    10   256    0 yes    131072  256    512  4500  4500 0xff 0xff
           lock           0     0     0    0 no          1    0      0  9000  9000 0x00 0x00
           lfuse          0     0     0    0 no          1    0      0  9000  9000 0x00 0x00
           hfuse          0     0     0    0 no          1    0      0  9000  9000 0x00 0x00
           efuse          0     0     0    0 no          1    0      0  9000  9000 0x00 0x00
           signature      0     0     0    0 no          3    0      0     0     0 0x00 0x00
           calibration    0     0     0    0 no          1    0      0     0     0 0x00 0x00

         Programmer Type : STK500V2
         Description     : Atmel STK500
         Programmer Model: AVRISP
         Hardware Version: 2
         Firmware Version Master : 2.10
         Vtarget         : 5.2 V
         SCK period      : 0.1 us

avrdude: AVR device initialized and ready to accept instructions

Reading | ################################################## | 100% 0.11s

avrdude: Device signature = 0x1e9705 (probably m1284p)
avrdude: safemode: hfuse reads as DC
avrdude: safemode: efuse reads as FD

avrdude: safemode: hfuse reads as DC
avrdude: safemode: efuse reads as FD
avrdude: safemode: Fuses OK (E:FD, H:DC, L:D6)

avrdude done.  Thank you.

```

## Read Existing Hex
```
"C:\Program Files (x86)\Arduino\hardware\tools\avr/bin/avrdude" -C"C:\Program Files (x86)\Arduino\hardware\tools\avr/etc/avrdude.conf" -v -patmega1284p -cstk500 -PCOM11 -U flash:r:MeltziStockFirmware.hex:r
```
