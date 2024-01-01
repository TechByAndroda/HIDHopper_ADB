# HIDHopper ADB

HIDHopper ADB is a modified (forked) version of adbuino and QuokkADB.  It is a Raspberry Pi Pico based hardware device which converts USB keyboard and mouse inputs to the Apple Desktop Bus (ADB) standard.

![HIDHopper_ADB Hardware Image](images/HIDHopper_Front_WithHat.jpg)

# Usage
See the file [doc/HIDHopper.md](https://github.com/TechByAndroda/HIDHopper_ADB/blob/master/doc/HIDHopper.md) for more full documentation

# Quick Usage
- For Base HIDHopper without USB Hub, plug into ADB and plug in your USB peripheral (mouse or keyboard).  Done.
- If you ordered the USB Hub, you *must use external power* to avoid blowing the ADB power fuse on your motherboard.  Power via the USB-C connector on the hub.
- Plug in desired USB keyboard and mouse, and go.

# Background

This is a fork of Difegue's version of the [adbuino](https://github.com/Difegue/Chaotic-Realm), which was a modified version of [bbraun's](http://synack.net/svn/adbduino/) PS/2 to ADB arduino sketch, with some extra code added to alleviate issues with his own PS/2 keyboard.  For Difegue's original write-up, please read more info [here.](https://tvc-16.science/adbuino-ps2.html).

# How to build and flash HIDHopper ADB

Note: This software is intended to be compiled in an Ubuntu Linux environment.

- Install the Raspberry Pi Pico SDK (https://github.com/raspberrypi/pico-sdk)
- Set the `$PICO_SDK_PATH` environment variable to your pico-sdk directory
- Open a Terminal and "cd" into this project
- From the top level of this project, "cd" to the `src/firmware` folder
- In Terminal, execute the following commands from the above `src/firmware` folder:
  - `mkdir build`
  - `cd build`
  - `cmake ..`
  - `make`
- The build outputs (.uf2, .bin, .elf, etc) will be placed in this folder (path is from the top level of the project):
  - `src/firmware/build/src`
- Next, plug the micro-USB side of a USB cable into HIDHopper
- Press the button on the Pico stick with a pencil or paperclip through the indicated hole on the case
- While holding down the button, plug the USB cable into your computer (then release the button after plugging in)
- You should see an "RPI-RP2" mass storage device appear on your computer
- Drag the ".uf2" file onto that mass storage device
- Once the mass storage device disappears, wait 10 seconds and then you are free to unplug

# References
![ADB Pinout](images/adb_pinout.png)

## Protocol/Software Documentation
- [Apple ADB Manager Documenation](https://developer.apple.com/library/archive/documentation/mac/pdf/Devices/ADB_Manager.pdf)
- [ADB Overview](https://www.lopaciuk.eu/2021/03/26/apple-adb-protocol.html)
- [Microchip Application Note AN591](http://www.t-es-t.hu/download/microchip/an591b.pdf)
- [TMK Documentation](https://github.com/tmk/tmk_keyboard/wiki/Apple-Desktop-Bus)

## Other libraries
- [TinyUSB Library](https://github.com/raspberrypi/tinyusb)
- [MiSTER adb hardware emulation](https://github.com/mist-devel/plus_too/blob/master/adb.v)

## Development resources
- [Running OpenOCD without root](https://forgge.github.io/theCore/guides/running-openocd-without-sudo.html)

## Hardware Links
- [ADB Connector - mouser](https://www.mouser.com/ProductDetail/TE-Connectivity/5749181-1?qs=XlZqES4cpWbRcAMR%2FcJqkQ%3D%3D)
