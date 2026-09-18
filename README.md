# ECE 528/L - Robotics and Embedded Systems Lab
**CSU Northridge**

**Department of Electrical and Computer Engineering**

## Overview

Title: Lab 0 - GPIO
Author: Dominic Sanqui
Date: 9/24/26

Description: The purpose of this lab was to introduce how to use the General Purpose Input/Output (GPIO) of the MSP432 Launchpad. For this lab, we configure the MSP432 Launchpad to have 2 types of inputs which are 2 buttons and 4 PMOD switches. Additionally, the MSP432 Launchpad was configured to have 2 types of outputs: LEDs built into the Launchpad and LEDs connected through a PMOD 8LD. Based on the values of the buttons and/or switches, the LEDs on the Launchpad and the PMOD will display a variety of patterns.

## Components Used
- 1 TI-RSLK MAX
- 1 PMOD SWT
- 1 PMOD 8LD
- 1 USB-A to Micro-USB Cable
- 1 Breadboard
- Female to Male Connectors

## Analysis and Results
- 

## Known issues or limitations
LED7 of the PMOD 8LD never turned on regardless of the value of the P9OUT register. This could be the result of damage to either the MCU or the PMOD 8LD itself. Since LED0-6 still work, I was able to still generate most of the expected outputs.

## References
* Technical Reference Manual for TI MSP432 Launchpad
[Product Link](https://web.archive.org/web/20200402132841/http:/www.ti.com/lit/ug/slau356i/slau356i.pdf)

* User buttons and LEDs of the TI MSP432 LaunchPad
* PMOD SWT (4 Slide Switches) - [Product Link](https://digilent.com/reference/pmod/pmodswt/start)
* PMOD 8LD (8 LEDs) - [Product Link](https://digilent.com/shop/pmod-8ld-eight-high-brightness-leds/)