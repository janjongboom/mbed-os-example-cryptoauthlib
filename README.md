# Mbed OS 5 example program for CryptoAuthLib

Example program to talk to Microchip CryptoAuth devices from Mbed OS. This application currently only supports I2C devices, but modifying it to also deal with SWI or UART should be relatively simple. The underlying library is here: [mbed-cryptoauthlib](https://github.com/janjongboom/mbed-cryptoauthlib).

Compatible with:

* ATSHA204A
* ATECC108A
* ATECC508A
* ATECC608A

Right-now it only searches for the CryptoAuth device on the *main* I2C bus.

## How to build

**Mbed CLI**

1. Import the program:

    ```
    $ mbed import https://github.com/janjongboom/mbed-os-example-cryptoauthlib
    ```

1. Build via:

    ```
    $ mbed compile -m SAML21J18A -t GCC_ARM
    ```

**Online Compiler**

1. Click *Import*.
1. Select *Click here to import from URL*.
1. Enter: `https://github.com/janjongboom/mbed-os-example-cryptoauthlib`
1. Click `OK`.
1. Click `Compile`.

## Running the application

1. Connect a serial monitor to the device on baud rate 115,200.
    * Under 'terminal settings' (or similar), make sure to select `CR+LF` for the return key.
1. Type `help` to list all commands.

E.g. to see the serial number on ATECC608A:

```
$ help
Usage:
help - Display Menu
discover - Discover Buses and Devices
204 - Set Target Device to ATSHA204A
108 - Set Target Device to ATECC108A
508 - Set Target Device to ATECC508A
608 - Set Target Device to ATECC608A
info - Get the Chip Revision
sernum - Get the Chip Serial Number
rand - Generate Some Random Numbers
readcfg - Read the Config Zone
lockstat - Zone Lock Status
lockcfg - Lock the Config Zone
lockdata - Lock Data and OTP Zones
all - Run all unit tests, locking as needed.
basic - Run Basic Test on Selected Device
unit - Run Unit Test on Selected Device
otpzero - Zero Out OTP Zone
util - Run Helper Function Tests
clkdivm0 - Set ATECC608A to ClockDivider M0(0x00)
clkdivm1 - Set ATECC608A to ClockDivider M1(0x05)
clkdivm2 - Set ATECC608A to ClockDivider M2(0x0D)
cd - Run Unit Tests on Cert Data
cio - Run Unit Test on Cert I/O
crypto - Run Unit Tests for Software Crypto Functions

$ 608
Device Selected.

$ sernum
serial number:
01 23 22 BA 34 78 82 A4 EE
```

## License

This example application is copyrighted by Microchip. See the LICENSE file.
