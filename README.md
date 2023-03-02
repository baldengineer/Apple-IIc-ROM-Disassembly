## Apple IIc Disassembly by Bald Engineer
For the [Mega IIe project](https://github.com/baldengineer/Mega-IIe/), I want to add Smart Port (or Protocol Converter or CBUS) support. 

My idea is to take the associated code out of the IIc ROM and shove it into the modified IIe ROM that I am using.

The challenge is that the SmartPort code is in bank2 and the Mega IIe did not wire the appropraite address line to the EEPROM. So, I need to shove the code into the IIe's ROM.

![SourceGen screenshot in the Slot 6 code](/images/IIc_rom3_slot6_code.png|width=600)
## ROM 3 (aka slinky)
Currently I am focused on ROM 3 aka 342-0445-A. It is the listing available in the [Apple IIc Technical Reference](https://archive.org/details/Apple_IIc_Technical_Reference_Manual). This is an updated version of the reference which includes the Memory Expandable IIc, aka slinky.

## Bank 1 and Bank 2
Sicne I am new to using 6502bench, I wasn't sure how to handle bank swapping. So I split the IIc ROM into two files: Bank 1 and Bank 2. My intention was to disassemble the separately. I may end up breaking down the ROMs even further than that.

Note, I've been bouncing back and forth between bank 1 and bank 2.

## 6502bench / SourceGen
The tool I'm using for diassembly is [SourceGen](https://6502bench.com/). It is Windows-only but it is very powerful. It can open the `.dis65` files found here.

A really nice feature of 6502bench is that it outputs the disassembly as a hotlinked HTML. (Which is my primary reason for doing this exercise.) 

See the note in the `RuntimeData` directory about the symbol files.

## Where to get the ROM?
You can download the binary files from various archive sites. However, to open them with the SourceGen files, you'll need to split the file `03-342-0445-A.bin` at the bank boundry $3FFF.