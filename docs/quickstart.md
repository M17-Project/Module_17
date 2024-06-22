# Quickstart guide

You have successfuly [flashed](./flashing.md) your Module17 and want to get started? This quickstart guide explains how to get on the air for the first time.

## Configure OpenRTX

The first thing to do is to configure OpenRTX. The only real change needed is to encode your callsign in the device. For that:
- Press "Enter"
- Select "M17" and press "Enter"
- Select "Callsign" and press "Enter"
- Input your callsign using "Up"/"Down" to select the correct letter and "Left/Right" to muve the cursor to the left/right. 
- Press "Enter" once you are done.

## Adjusting the baseband levels

### Check your transceiver compatibility

[This wiki page](https://wiki.m17project.org/radio_compatibility) contains a non-exhaustive list of the known compatible transceiver. Check if yours is in the list. If it is not, you will need to test it. Please submit an issue [here](https://github.com/M17-Project/wiki/issues) once you are done testing your radio.

### Adjust the baseband level

The precise level of the baseband signal needs to be tuned to your radio's requirements. You will need to adjust both the RX and TX levels separately.

Depending on the variant of your board, the level tuning is done with digital potentiometers or multiturn potentiometers. 

The multiturn potentiometers need to be adjusted with a small screwdriver.

The digital potentiometers need to be adjusted from within OpenRTX. For that, power-up your Module17 and:
- Press "Enter"
- Select "Settings" and press "Enter"
- Select "Module17" and press "Enter"
- Select the baseband signal you want to adjust. Adjust the level using the "Left"/"Right" keys.

#### Adjusting TX level

The most reliable way to tune the TX baseband signal level is using SDR++ and an SDR receiver (like an RTL-SDR). 

- Connect your Module17 to your radio
- Add an M17 demodulator module to your SDR++ interface and tune it to the frequency of your radio
- In the m17_decoder module you added, tick the "Show Reference Lines" box
- While pressing the PTT, have a look at the symbols graph of the m17\_decoder module and adjust the baseband TX level until the blue dots line-up with the gray lines in the background
- When the baseband level is properly adjusted, the m17_decoder should correctly decode your signal. If it does not, check your TX baseband polarity. If it still does not work, your radio may be incompatible.

#### Adjusting RX baseband level

A proper RX baseband level adjustment is not as crucial as for TX baseband. You should set it so that the peak-to-peak voltage of the RX baseband signal (on testpoint labeled `BB_RX`) is right under 3.3V. Anything above that means that the signal will be saturating in the MCU. Anything below that means that you are not using the full dynamic range of the analog-to-digital converter.

In order to measure the level on the testpoint, you can use an oscilloscope if you have one. You can also use a digital multimerer (but pay attention that the value displayed will **NOT** be the peak-to-peak voltage but the RMS voltage; in that case aim vor an RMS value of 1.1V). You should measure this voltage while receiving an M17 baseband signal.

If the signal is tuned to the proper level but the board cannot demodulate the incoming signal then check the RX baseband signal polarity. If it still does not work, then your radio may be incompatible.

### Adjust the baseband polarity

The polarity of the baseband signal may need to be modified depending on your specific radio. If your radio is listed in the compatibility list linked above then you can re-use the settings from that list. Otherwise you will need to try both settings for RX and TX to check which one works.
