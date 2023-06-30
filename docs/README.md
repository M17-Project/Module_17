# Module 17
Welcome to Module 17!

This project provides a standalone _smart microphone_ that transforms any 9600 baud capable transceiver into an [M17](https://m17project.org/) compatible radio. It is based on a STM32F4 microcontroller and is designed to run the [OpenRTX](https://openrtx.org/) firmware. Audio and PTT connectivity is given through a "Kenwood 2 Pin" compatible connector (2.5 and 3.5mm audio jacks).

![logo](_media/Module17_0.1e.jpg ':size=25%')

Several boards of various revisions have been built. While the changes between r0.1a and r0.1b were quite drastic, r0.1c and d are only minor revisions, mainly for parts availability. The pinout, baseband filters and components are considered stable and will (probably) not change in future revisions, ensuring software compatibility. Revision 0.1d boards can be ordered partially or even fully assembled at [JLCPCB](https://www.jlcpcb.com) with the manufacturing data in this repository. The volume knob and digital potentiometers are only available through Mouser/Digikey, but JLCPCB can acquire them through their global sourcing program.

Basic OpenRTX support is already given, but the UI needs an overhaul for Module 17. 

## Acknowledgments
This project is inspired by David Rowe's [SM1000](https://www.rowetel.com/wordpress/?p=3125) Codec2 smart mic and shares some of its circuitry. The analog baseband filtering is inspired by the [MMDVM_RPT_Hat](https://github.com/mathisschmieder/MMDVM_RPT_Hat) and is a simplified version of F0DEI's original filter design that is used with great success at many MMDVM repeater sites.

## License
Module 17 is licensed under the [TAPR Open Hardware License](https://tapr.org/the-tapr-open-hardware-license/)
