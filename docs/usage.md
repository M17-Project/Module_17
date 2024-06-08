## Usage (rev 1.0)

### Power supply
The modem can be supplied with:
- a 6..15V source via the DC plug (left of the USB-C socket) or pin 9 of the DE9 connector (upper right hand side),
- 5V through the USB-C connector (in the middle of the right side)
Both inputs can be used at the same time.

When power is supplied through the barrel jack (DC plug) the board can be powered on using the power button and powered off in the menu of the board (Enter -> Select Shutdown -> Enter)

When power is supplied through the USB-C socket, the board is always powered on and cannot be powered off.

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
On the left hand side of the board, there is a Kenwood-type connector. The pinout is standard and most microphone-speakers should be compatible with Module17. In particular, the microphone-speakers from Baofeng, TYT and Retevis have been tested and are compatible.

### OHIS connector
The board provides an OHIS connector if you want to use other audio devices than classical microphone-speakers. The connector does not provide the optional 5V output. See [OHIS Website](https://ohis.org/) for more information.

### Volume knob
The volume knob is at the bottom left part of the board. As the name suggests, it is used for audio volume setting. 

### Transmission/reception
At idle, the device will look for valid M17 signal in the baseband. If there is a valid signal detected carrying voice data, it will be decoded and sent to the speaker outputs at the Kenwood  connector. There is also an additional, unpopulated, 2-pin speaker connector in the left part of the modem. It can be used to connect an external >=8ohms speaker.
Transmission is triggered by the PTT key of the mic-speaker or OHIS connector. A valid baseband signal along with a PTT signal is then sent to the radio.

### CAT control
The hardware is ready for CAT signal to control a transceiver using the modem but OpenRTX does not implement it yet. It can not be used out of the box and you would need to implement it manually to use it. There is hardware support for logical level selection (3.3V or 5V). (June 2024)

### RTC Battery
The hardware has a microblade connector to enable you to connect a 3V lithium battery to supply the real time clock inside the microcontroller. OpenRTX does not implement RTC management for Module17 yet. (June 2024)

## Advanced features

### Test points

Multiple test points are available on the PCB to allow you to check the values of all the various signals (audio, baseband, power supplies, ...). Those are labeled with the signal they expose.

### Debug port

A debug port is available on the top part of the modem. It exposes the signals for the ARM SWD port of the microcontroller.

### Serial port

A serial port is exposed on the top part of the modem. It allows you to, for example, add a GPS chip (there is currently no software support for GPS). (June 2024)

