# PS/2 Model 80 1MB/2MB Memory Card Clone

IBM PS/2 Model 80 computers use a proprietary memory card instead of the more
common SIMM memory modules. I've reverse engineered a 3rd party memory board
that uses standard memory chips instead of the MST modules that the IBM
cards use. If you can't get an original card, or if the MST modules on your
card have gone bad, this project may be a good way to get your computer
back up and running.

![Photo of the board](ps2_80_memory.jpg)

[Schematic](ps2_80_memory.pdf)

[Fab Files](fab/ps2_80_memory-rev1.zip)

## Fabrication Notes

This is a 4-layer board. The stackup is not critical and the two inner layers
are just power and ground. The dimensions are 98.6 x 100mm. The thickness is
the standard 0.062" (1.6mm). 

## Bill of Materials

| Q  | Designator | Description       | MFG PN              | Mouser P/N         |
|----|------------|-------------------|---------------------|--------------------|
| 1  | J1         | DIN41612\_R\_3x32 | HARTING 09732966801 | 617-09-73-296-6801 |
| 26 | C1 - C26   | Cap, 0.1uF 25V 0603 | (Generic)         | |
| 2  | U1, U2     | 74F244 or AM2966PC | 74F244             | 595-SN74F244N |
| 16 | U3 - U18   | 256K x 4 DRAM, 80ns or faster | 44C256  | |
| 8  | U19 - U26  | 256K x 1 DRAM, 80ns or faster | 41C256  | |
| 1  | R1         | 0 ohm resistor, 0805 | | |
| 0  | R2         | DNI | | |
| 0  | R3         | DNI | | |

This bill of materials is for the full 2MB version of the card. For 1MB, populate as follows

| Q  | Designator | Description       | MFG PN              | Mouser P/N         |
|----|------------|-------------------|---------------------|--------------------|
| 1  | J1         | DIN41612\_R\_3x32 | HARTING 09732966801 | 617-09-73-296-6801 |
| 26 | C1 - C26   | Cap, 0.1uF 25V 0603 | (Generic)         | |
| 2  | U1, U2     | 74F244 or AM2966PC | 74F244             | 595-SN74F244N |
| 8  | U3 - U10   | 256K x 4 DRAM, 80ns or faster | 44C256  | |
| 4  | U19, U21, U23, U25 | 256K x 1 DRAM, 80ns or faster | 41C256 | |
| 2  | R1, R2     | 0 ohm resistor, 0805 | | |
| 0  | R3         | DNI | | |

## Assembly Notes

Assemble according to the bill of materials for the 1MB or 2MB version.
Besides the chips, the only other difference is jumper R2, which, when placed,
indicates to the computer that only 1MB is installed. You may want to omit
the extra bypass capacitors if you're only installing 1MB, but for flexibility,
I recommend socketing all the chips and including all the memory so it is easy
to switch back and forth.

## Troubleshooting

As with any accessory for the IBM PS/2 family of computers, troubleshooting
involves frustration and arcane knowledge. I recommend the following resources

* [IBM 8580 Common Devices](https://www.ardent-tool.com/8580/Common.html) - See the sections on memory
* [IBM 8580 Planar Memory](https://www.ardent-tool.com/8580/Memory.html)

The BIOS does some "intelligent" things, like swapping around blocks of memory,
which can make troubleshooting difficult.


## License
This work is licensed under a Creative Commons Attribution-ShareAlike 4.0
International License. See [https://creativecommons.org/licenses/by-sa/4.0/](https://creativecommons.org/licenses/by-sa/4.0/).

