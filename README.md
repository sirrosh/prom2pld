# PROM to PLD
A small tool to convert PROM binary dump into WinCUPL PLD description.
This gives a convinient way to repair bipolar fusable PROMs in old video games and 8-bit computers. 

As an example here we have a dump from N82S129 (1kbit=256x4) converted into Atmel's ATF16V8B for almost pin-to-pin exchange (inserting ATF pin 1 to 1 and 20 to 16, see PLD file for pin description). Only the ground (pin 10) should be wired extra.

A neat bash script (bin2pld) is written to convert a binary dump into a table function for PLD file.

Microchip provides WinCupl free of charge to deal with ATFxxx PLDs, can be officially [downloaded here](https://www.microchip.com/en-us/products/fpgas-and-plds/spld-cplds/pld-design-resources)

**IMPORTANT!** 
In order to compile the table function successfully you should turn on the Quine-McCluskey logic optimisation by pressing Ctrl+W (compiler options), "Minimization" tab. You may also run out of nodes despite minimization, try turning on "Best for polarity" checkox in "Optimization" tab.
