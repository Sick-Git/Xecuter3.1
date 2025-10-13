# Xecuter3.1

<img width="1044" height="1044" alt="X3 1 bottom" src="https://github.com/user-attachments/assets/4f689937-9f95-4f4b-9a50-14150ca86519" />


Open source repo of an updated Xecuter 3 for the original xbox.

New PCB manually routed & designed in Autodesk Eagle.
PCB gerbers in their respective folder.

This design incorporates a simple opti-SSR device (5A) to control the +5V from the LPC port, which is 'always on' in version 1.6 consoles which caused a problem of the 5V tsop chips (2) and any connected LCD screen being on with the V1.6 Xbox switched off, but plugged into the mains. This now means you no longer need the messy +5V wire soldering to the voltage regulator anymore.
A large protection diode is added to protect the SSR from any inductive reverse current (unlikely) since the LCD is generally resistive, but even a wire has some inductance. An optional inline fuse for 5V is also there should you wish to add it, if not simply add a zero ohm resistor.
Opti-SSR by Vishay has no bounce or noise in operation. You can also opt not to include the SSR V1.6 circuit entirely by simply adding zero ohm jumpers and leave off the diode as well for building specifically for Xbox versions 1.0 to 1.4.

Overall size brought in to fractionally smaller than an original purple Xecuter 3.
Added 5V filtering added for the TSOP's supply.
Capacitors C1 & C2 brought in to CPLD pins as per pdf (like X3).
Traces & placements optimised. (Lot of work)

LCD 20 pin connector footprint modified to accept both vertical (purple X3) and horizontal (X3CE) type connectors. Watch your orientation, match the markers I have placed on the board for vertical.
LCD contrast pot fooprint with twin resistor pads (R12 & R13) for tuning in pots from R10K to R20K due to scarce availability of thumbwheel pots of this size/pinout.
Correct orientation of D0/HDD/LAN connector. All connectors now match original Xecuter 3 chips, but see BOM for power/eject connector cable is pin 1 to pin 1 for Xecuter 3.1 (V1.6 +5V connector now not required).
New Xecuter 3.1 logo.

Order your PCB's in 1.2mm thick (best preference) and trim excess length of LPC header pins upon soldering in place for clean effect.
Onboard BIOS protect switch has been removed due to added confusion for users troubleshooting BIOS flashing and historical problems of switches going dry contact etc. (DuoX cited as example of this)
Also removes possibility of having flash protect switch on and having to disassemble whole xbox just to flash chip again! (X3 has backup flash and external flash protect anyway)

BOM (bill of materials) added.

The CPLD firmware has been compiled for you as the software to do this is both complicated for the average user and difficult to get hold of. The aim of this github is simply to make this available, easier and a slightly improved X3 overall for people to make themselves.

Be aware the main flash TSOP chip has a few manufacturers including Fujitsu which have the wrong device ID's for this application. Make sure they are AMD made and ID with your supplier.
(Updates to this github may come in due course to address TSOP ID's to add more ID's)

After extensive investigation I can confirm that the original Xecuter 3 'Backup 256k' TSOP chip is in fact made by EON and is EON EN29F002ANT (top boot). This is generally unavailable though.

I am also working to add OLED support to the original VHDL by Kekule used here.

<img width="1042" height="1047" alt="X3 1 top" src="https://github.com/user-attachments/assets/8fa560ec-5106-40b0-854a-c1459ddcdde7" />


<img width="1058" height="1040" alt="X3 1" src="https://github.com/user-attachments/assets/b956b4c4-f36f-4013-aef8-a84dae217ca9" />


Mentions,

Kekule - VHDL

Team-Donkey - open X3

Ryzee119 - VHDL

Ernegien - Registers


