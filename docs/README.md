# Module 17
Welcome to Module 17!

This project provides a standalone _smart microphone_ that transforms any 9600 baud capable transceiver into an [M17](https://m17project.org/) compatible radio. It is based on a STM32F4 microcontroller and is designed to run the [OpenRTX](https://openrtx.org/) firmware. Audio and PTT connectivity is given through a "Kenwood 2 Pin" compatible connector (2.5 and 3.5mm audio jacks) or an [OHIS](https://ohis.org/) connector (this is **NOT** an internet connector).

![logo](_media/Module17_rev1.0_bare_front.jpg ':size=25%')

Several boards of various revisions have been built. The latest one is rev 1.0. This revision went through a complete board re-design, mainly to make it compatible with an aluminium extruded enclosure. It does however remain very similar in principle to the previous revisions. Other changes such as audio input and output improvements were made in this revision.

Revision 1.0 boards can be ordered partially or even fully assembled at [JLCPCB](https://www.jlcpcb.com) with the manufacturing data in this repository. Some parts such as the digital potentiometers, the DC-DC converter inductor or the audio power amplifier may not (always) be in stock at JLCPCB. Though they are almost always available through Mouser/Digikey. JLCPCB can acquire them through their global sourcing program if you are willing to use it.

## Acknowledgments
This project is inspired by David Rowe's [SM1000](https://www.rowetel.com/wordpress/?p=3125) Codec2 smart mic and shares some of its circuitry. The analog baseband filtering is inspired by the [MMDVM_RPT_Hat](https://github.com/mathisschmieder/MMDVM_RPT_Hat) and is a simplified version of F0DEI's original filter design that is used with great success at many MMDVM repeater sites.

## License
Module 17 is licensed under the [TAPR Open Hardware License](https://tapr.org/the-tapr-open-hardware-license/)
