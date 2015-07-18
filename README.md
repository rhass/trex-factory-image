Dumped with AVRDude 6.0.1.

Dumping Flash and EEPROM
========================
 - Dumping Flash: `$ avrdude -F -v -pm328p -cstk500v1 -P/dev/ttyUSB0 -b57600 -D -Uflash:r:trex-factory-image_flash.bin:r`
 - Dumping EEPROM: `$ avrdude -F -v -pm328p -cstk500v1 -P/dev/ttyUSB0 -b57600 -D -Uflash:r:trex-factory-image_eeprom.bin:r`

Expected Output when Dumping Flash
==================================
```
avrdude: Version 6.0.1, compiled on Oct 21 2013 at 15:55:32
         Copyright (c) 2000-2005 Brian Dean, http://www.bdmicro.com/
         Copyright (c) 2007-2009 Joerg Wunsch

         System wide configuration file is "/etc/avrdude.conf"
         User configuration file is "/home/rhass/.avrduderc"
         User configuration file does not exist or is not a regular file, skipping

         Using Port                    : /dev/ttyUSB0
         Using Programmer              : stk500v1
         Overriding Baud Rate          : 57600
         AVR Part                      : ATmega328P
         Chip Erase delay              : 9000 us
         PAGEL                         : PD7
         BS2                           : PC2
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
           eeprom        65    20     4    0 no       1024    4      0  3600  3600 0xff 0xff
           flash         65     6   128    0 yes     32768  128    256  4500  4500 0xff 0xff
           lfuse          0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           hfuse          0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           efuse          0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           lock           0     0     0    0 no          1    0      0  4500  4500 0x00 0x00
           calibration    0     0     0    0 no          1    0      0     0     0 0x00 0x00
           signature      0     0     0    0 no          3    0      0     0     0 0x00 0x00

         Programmer Type : STK500
         Description     : Atmel STK500 Version 1.x firmware
         Hardware Version: 2
         Firmware Version: 1.16
         Vtarget         : 0.0 V
         Varef           : 0.0 V
         Oscillator      : Off
         SCK period      : 0.1 us

avrdude: AVR device initialized and ready to accept instructions

Reading | ################################################## | 100% 0.01s

avrdude: Device signature = 0x1e950f
avrdude: safemode: lfuse reads as 0
avrdude: safemode: hfuse reads as 0
avrdude: safemode: efuse reads as 0
avrdude: reading flash memory:

Reading | ################################################## | 100% 6.46s

avrdude: writing output file "trex-factory-image_flash.bin"

avrdude: safemode: lfuse reads as 0
avrdude: safemode: hfuse reads as 0
avrdude: safemode: efuse reads as 0
avrdude: safemode: Fuses OK (H:00, E:00, L:00)

avrdude done.  Thank you.
```

Restoring Flash and EEPROM Data
================================
 - Restoring Flash:
`$ avrdude -F -v -pm328p -cstk500v1 -P/dev/ttyUSB0 -b57600 -D -Uflash:w:trex-factory-image_flash.bin:r`
 - Restoring EEPROM:
`$ avrdude -F -v -pm328p -cstk500v1 -P/dev/ttyUSB0 -b57600 -D -Ueeprom:w:trex-factory-image_eeprom.bin:r`
