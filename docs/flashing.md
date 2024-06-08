## Flashing

### Entering DFU mode
To flash the board, you need to put it in DFU mode. The procedure to do so will depend whether you use the HMI board or not.

#### Using the bare modem board (rev 1.0)
Hold the "Escape" (upper left) button down while pressing the reset switch (upper left corner of the board) or plugging in the USB cable.

#### Using the HMI and enclosure (rev 1.0)
First put the switch on the rear of the device to the "FW Update" position then either plug in the USB cable or press the reset switch (bottom left corner of the front face of the device). When the device is in DFU mode, you can then put the switch on the rear of the device back to the "Run" position.

#### Using the bare modem board (revisions 0.1a to 0.1e)
Hold the "Escape" (upper left) button down while pressing the reset switch (left side of the board, abode the kenwood connectors) or plugging in the USB cable.

### Linux
To flash, you first need to put the device in DFU mode (see above).

You need `dfu-util` 0.11 to start the process. `dfu-util` installation instructions are [here](https://dfu-util.sourceforge.net/build.html). It is recommended to use the most recent version - built from source.

For your convenience, a pre-built binary is available [here](https://files.openrtx.org/nightly/) and [here](https://openrtx.schinken-radio.de/nightly/). The name of the file is `openrtx_mod17_wrap`.
You can then follow standard [OpenRTX](https://github.com/OpenRTX/OpenRTX)
flashing instructions for the "mod17" target if you have dfu-util
installed:<br>
`dfu-util -d 0483:df11 -a 0 -D openrtx_mod17_wrap -s 0x08000000`

Once flashing is complete, reset the board to boot into the newly flashed application. If there are any errors while flashing, make sure there's a valid udev rule available for the Module17. Download the [udev](https://github.com/OpenRTX/OpenRTX/blob/master/99-openrtx.rules) file and then run the following commands:<br>
`sudo cp 99-openrtx.rules /etc/udev/rules.d`<br>
`sudo udevadm control --reload-rules`.

### Windows
To flash, you first need to put the device in DFU mode (see above).

Be sure that you have WinUSB installed for your DFU device. You can use [Zadig](https://zadig.akeo.ie/). After the Module17 is connected and in DFU mode, select it from the list in Zadig, then install the driver.

- Download the [dfu-util-0.11-binaries.tar.xz dfu-util binary for Windows](https://dfu-util.sourceforge.net/releases/) and unzip.
- Download the `openrtx_mod17_wrap` file, it's available [here](https://files.openrtx.org/nightly/) and [here](https://openrtx.schinken-radio.de/nightly/).
- Navigate to `{extraction_location}\dfu-util-0.11-binaries\win64` (or `win32`) and copy the wrap file there. Example path: `C:\Users\SP5WWP\Desktop\dfu-util-0.11-binaries\win64`.
- Run the command prompt (`cmd`) as administrator and change the working directory with `cd {extraction_location}\dfu-util-0.11-binaries\win64`.
- Run the following command: `dfu-util -d 0483:df11 -a 0 -D openrtx_mod17_wrap -s 0x08000000`
- After the flashing is complete, close the command prompt and reset the device.

### Building the firmware yourself
Building instructions are available [at the OpenRTX project's website](https://openrtx.org/#/compiling).<br>