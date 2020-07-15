---
title: Setting Up a New Pi Zero
parent: Setup
has_children: false
nav_order: 1
---


# Raspberry Pi Zero Clean Install


Updated install instructions for adding I2C sensors: Altimeter(BMP280), Accelerometer


Doing a clean install on a Pi Zero
- Setup Pi Zero :
    - Regular NOOBs install,
    - Get Wifi network connected using Rpi GUI Desktop
    - Get Putty connected
    - Get WinScp connected
        sudo rasp-config
- Set boot option to “Console Autologin Text console, automatically logged in as 'pi'”
- Rename host as desired (pi-zero-131)
- Set time zone (Pacific-new)
- Change password to (raspberry!)
- Localization options:
    - USA,
    - KB: US
- Interfacing options:
    - Enable Camera
    - Enable SSH
    - Enable I2C
    - Serial
    - Disable login shell
- Enable Serial port hardware
```
    pip3 install digi-xbee
    pip3 install pytimeparse
    pip3 install RPI.GPIO
    pip3 install adafruit-blinka
    pip3 install adafruit-circuitpython-lis3dh
    pip3 install adafruit-circuitpython-busdevice
    sudo pip3 install adafruit-circuitpython-bmp280
    sudo pip3 install adafruit-circuitpython-mma8451
    sudo vi /etc/udev/rules.d/50-usb.rules
    SUBSYSTEM=="tty", ATTRS{idVendor}=="0403", ATTRS{idProduct}=="6001", SYMLINK+="XB0"
```

- This works for both Grove Devel Board and SMD card USB Adapter board
- Check i2C devices: ```i2cdetect -y 1```
- Verify 0x18 address (LIS3DH 3 axis accel)
- Verify 0x77 address (BMP280 pressure/temp sensor):
    python3 bmp280_simpletest.py
    python3 accel_test.py
- Copy the source code onto the Pi
- Test, then backup the SD card using Win32DiskImager


Additional packages for clean install on ground system Raspberry Pi 3:
```
    sudo apt-get update
    sudo apt-get install build-essential python-dev python-pip
    sudo apt-get install python-imaging python-smbus
    sudo apt-get install git
    sudo apt-get install -y mpg123
    sudo apt-get install ffprobe
    sudo apt-get install sox
    sudo pip install RPi.GPIO
    pip3 install pytimeparse
```
