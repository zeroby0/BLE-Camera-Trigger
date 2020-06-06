# BLE Camera Trigger

You can trigger camera capture on Android devices with an nRF-52DK with this code.

This is just a modification of the BLE_HID_Keyboard example to send '\n' on button press.
Press Button-1 for capture. Read [this page](https://developer.nordicsemi.com/nRF_Connect_SDK/doc/latest/nrf/samples/bluetooth/peripheral_hids_keyboard/README.html)
for more details.

## Uses

I use this to capture photos from my telescope without touching the phone and disturbing the camera.
If you have friends, you can take a group photo while you're in it.


## Requirements

The [nRF52DK](https://www.nordicsemi.com/Software-and-Tools/Development-Kits/nRF52-DK).
Or a custom nRF52 based board with a button on it.


# Setup

## MacOS

1. Download nRF SDK from Nordic Semiconductors' website
2. Unzip SDK and place it in project root (or wherever you want, really)
3. Download [GNU ARM](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads) Embedded toolchain.
4. Unzip ARM tool chain and place it in /usr/local 
5. Download and install JLink software from [Segger](http://www.segger.com/jlink-software.html).
6. Install [NRF Jprog](https://www.nordicsemi.com/Software-and-tools/Development-Tools/nRF-Command-Line-Tools).
7. Also, you'll need to have Make installed. Comes with XCode if it's not installed by default.
8. Now edit SDK/components/toolchain/gcc/Makefile.posix. You'll need to update GCC_INSTALL_ROOT and GNU_VERSION. I found my version at /usr/local/gcc-arm-none-eabi-9-2019-q4-major/lib/gcc/arm-none-eabi


That's it! Open a terminal in one of the examples' armgcc folder and run `make` to compile.. `make flash_softdevice` to upload the Softdevice, and `make flash` to flash the chip.
Remember to edit the Makefile to set the SDK location correctly.
Run `make erase`, `make flash_softdevice`, and `make flash` if you need to connect to a new device.
This software acts as a HID Keyboard, and may hide the virtual onscreen keyboard.
That can be changed in the settings.


