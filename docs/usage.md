## Usage (rev 0.1d/e)
### Power supply
The modem can be supplied with:
- a 6..15V source via the DC plug (upper right hand side) or pin 9 of the DE9 connector (upper left hand side),
- 5V through the USB-C connector (in the middle of the upper side)
Both inputs can be used at the same time.

### DE-9 connector
The DE-9 connector at the top of the board can be used to connect Module17 to a 9600baud radio. The pinout is shown in the table below.

| Pin      |             Function             |             Direction            | `CT-167` cable wire color |
|----------|:--------------------------------:|----------------------------------|---------------------------|
| 1        |  unused (floating)               |  --                              |                           |
| 2        |  baseband output (towards radio) |  output                          |  brown                    |
| 3        |  CAT-RX                          |  input                           |                           |
| 4        |  CAT-TX                          |  output                          |                           |
| 5        |  radio PTT                       |  output, open-drain, low-active  |  red                      |
| 6        |  baseband input (from radio)     |  input                           |  orange                   |
| 7        |  unused (floating)               |  --                              |                           |
| 8        |  ground                          |  --                              |  black, thick             |
| 9        |  12V input                       | input (supply)                   |                           |

![CT-167 Wiring](_media/CT-167.png ':size=75%')

Additionally, there is a 2.54mm pin header just next to the DE-9 connector that can be used for convenient access to the baseband, PTT and CAT signals. Pin 9 doesn't have to be used, it only provides an alternative way for supplying the board.  

### Kenwood mic-speaker connector
On the left hand side of the board, there is a Kenwood-type connector. The pinout is standard and most microphone-speakers should be compatible with Module17.

### Volume knob with a power switch
The volume knob is at the bottom of the board. As the name suggests, it is used for audio volume setting. It also acts as the power switch for the module. **Note** - the power switch is on the 12V line, so it is not possible to turn the device off while it is powered with 5V (USB).

### Transmission/reception
At idle, the device will look for valid M17 signal in the baseband. If there is a valid signal detected carrying voice data, it will be decoded and sent to the speaker at the Kenwood  connector. There is also an additional, unpopulated, 2-pin speaker connector in the lower left corner of the modem. It can be used to connect an external >=8ohms speaker.
Transmission is triggered by the PTT key of the mic-speaker. A valid baseband along with a PTT signal is then sent to the radio.

**Warning** - OpenRTX does not yet support phase inversion of the baseband. Channel Access Number is not settable. CAT protocol is not implemented yet. (November 2022)