# BMP280 Arduino Library
======================

This library uses I2C communication to read the Temperature( degC) , Pressure (mBar) and Altitude (m).

Modified by John Greenwell to adapt driver for custom HAL support, 2025.

## Usage

For this modified version, the following hardware abstraction layer (HAL) requirements must be satisfied:

* A header file `hal.h` providing access to HAL classes and methods.
* An `I2C` class within the `HAL` namespace with the following methods:
  - Write one byte to the device, execute a repeated start, then read n bytes from the device: `writeRead(uint8_t device_address, uint8_t register, uint8_t * data_buffer, uint32_t length_in_bytes)`
  - Read n bytes from the device:`read(uint8_t device_address, uint8_t * data_buffer, uint32_t length_in_bytes)`.

Some further requirements may also be found. Typically, these will mirror the Arduino framework and should be added to `hal.h`.

## Pin Connection : 
======

BMP280-----Arduino

VDD   ----> 3.3V

GND   ----> GND

SDA   ----> PIN20 (arduino mega, changeable in begin) 

SCL   ----> PIN21 (arduino mega, changeable in begin)

SDO   ----> GND   (slave address 0x76)

CS    ----> VDD   (HIGH for I2C)

VDDIO ----> VDD


## Instructions :
=============

Copy the BMP280 folder to Arduino/libraries

Restart Arduino and Upload "measurments" sketch in Arduino.




