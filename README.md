## Note: This is a fork of ![AT28C-EEPROM-Programmer-Arduino](https://github.com/crmaykish/AT28C-EEPROM-Programmer-Arduino).
## The aim of this fork is to fix issues I found during usage of the original and to add KiCad files for an ATMEGA 

# AT28C EEPROM Programmer for Arduino Mega

This is a simple way to program Atmel AT28C-style EEPROMs with an Arduino Mega.

There are two pieces: the Arduino firmware and the Python CLI.

## Setup

1) Wire up the Arduino as shown in the breadboard diagram below. Don't forget the 10kohm pullup resistor on the WE pin.
2) Flash the firmware to the Arduino.
3) Create a virtual environment
4) Install the requirements from requirements.txt
5) Run the Python CLI tool.

## Changes



## Usage

Read the first 20 bytes of the EEPROM:
`python3 at28c_programmer.py -d /dev/ttyACM0 -r -l 20`

Flash a binary file to the EEPROM:
`python3 at28c_programmer.py -d /dev/ttyACM0 -w -f file.bin`

## Notes

1. This writes one byte at a time over the serial port. It is slow... If you have to flash huge binary files, you're probably better off with an off-the-shelf EEPROM programmer, but if you want to save $60, this will work for small files.
2. The `-w` write command also supports a limit `-l x` limit parameter. This will limit the writes to the first x bytes. Might be useful if your EEPROM binary file is padded with zeroes.

## Circuit

![Breadboard Diagram](at28c_programmer_bb.png)


