## Revisions
### Revision 0.1a
This is the initial prototyping revision and not yet designed with "ease of use and enclosing" in mind. Its main purpose is getting OpenRTX up and running on the hardware and providing a proof of concept.

#### Errata of Revision 0.1a
* Do not install R23 (1k5 pull-up on USB D+) as the STM32F4 has an integrated pull-up
* Replace C3 and C6 with 18pF, otherwise Y1 starts too slow during USB DFU
* Short BOOT0 on pin 94 to PB8 on pin 95 to be able to use SW4 in software
* The 2.5mm mono jack used for the Kenwood 2-pin speaker mic has the "sleeve" connection where stereo plugs have the "ring". This means that the speaker mic has no GND connection. To fix this, add a bodge wire to the outer shell of the mono jack to GND. Next revisions will use a stereo jack with shorted ring and sleeve connections.

### Revision 0.1b
Fixed some bugs:
* Changed audio amp from LM386 to LM4861MX
* Mic amplifier changed from LMV341 to MAX9814 (with an AGC)
* Fixed Kenwood connector
* Fixed baseband processing at U6/U7
* C3/C6 value change from 22 to 18p
* Changed micro from STM32F407VETx to -405RGTx
* Added TPS5431 DC/DC converter IC
* Added MAX3232 and `CAT_TX`/`CAT_RX` at DE9 connector

### Revision 0.1c
* Reduced audio amplifier gain (R3 value change 510k->22k)
* Fixed `RADIO_RX` baseband DC bias

### Revision 0.1d
* Changed supply voltage for U6 and U7 (baseband filter Op-Amps) to 5V and replaced MCP602 with MCP6002 as the former ICs are not rail2rail capable on their input
* Fixed `CAT_TX` and `CAT_RX` solder jumpers
* Fixed volume knob direction
* Replaced PSU with in-stock parts
* Replaced MAX3232 with simple 5V/3.3V level shifters as most, if not all, radios use either 5V or 3.3V TTL instead of RS232
* Replaced STM32F405RGT6 with GD32F405RGT6 - these ICs are pin and code compatible

### Revision 0.1e
* Replaced digital potentiometers with multiturn ones to improve parts availability
* Moved the TX potentiometer from the op-amp's output to between STM32 and the first op-amp
* Added power-on button
* Fixed misc BOM errors and removed a few unnecessary components from the schematic

#### Errata of Revision 0.1e
R31 has too high value. Add a 2.2k resistor across it (in parallel) to increase the sound volume coming from the speaker. Alternatively, replace R31 with a 1.8k or 2k resistor.

### Future revisions
Future revisions will feature at least additional power supply options and will be designed with an enclosure in mind.