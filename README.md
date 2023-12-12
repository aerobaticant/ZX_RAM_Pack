# ZX RAM Pack
This is my design for a RAM pack for the Sinclair ZX81 computer.
<br>It uses a 62256 SRAM IC to give 32KiB of RAM available to BASIC.

## PLD
A 16V8 PLD is used to do the address decoding.

RAM is enabled when A13, A14 or A15 are high ($2000-$FFFF)
<br>RAM area $4000-$7FFF is shadowed at $C000-$FFFF

RAM is read during MREQ or RFSH to allow Hi Res Graphics

ROM shadow is disabled when A15 is high ($8000-$BFFF)
<br>Note: ZX80 has no ROMCS signal so ROM shadow can't be disabled
<br>This means the ZX80 can only be given 16K

ROM is also disabled in address $0004 following reset to allow auto detection
<br>Pull-ups on the data bus generate LD BC,$FFFF instead of LD BC,$7FFF for RAM-CHECK

## Schematic
The Schematic and PCB were created in KiCAD

## STLs
I have also created a 3D printable enclosure based on the design of the original ZX80's 3KB RAM pack.
<br>You may have to rotate the parts to suit your 3D printer.
