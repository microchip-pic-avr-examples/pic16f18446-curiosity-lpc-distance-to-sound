# Introduction

In this project I use the ADCC of the PIC16F18446 to read the IR Distance Sensor. Then I use NCO to generate a tone with variable pitch according to the distance reading.

![Demo Setup](./images/1.jpg)

# Description

In this demo,

- PIC16F18446 (20-pin, PDIP) MCU is used to read the IR Distance Click and generate an adjustable frequency square signal.
- The Curiosity development board is used as it supports a mikroBUS slot for MikroElektronika™ click boards and has got on-board programmer and debugger.
- The IR Distance Click board from MikroElektronika™ is used for sensing the distance.
- A set of headphones in used to hear the output sound. The IR Distance sensor is read using the PIC's ADCC. In order to hear the sound, the headphone set must be connected in series with 1k resistor to RC1 and GND.

# Software Tools

Make sure the latest MCC libraries for PIC16F18446 MCU are installed. The demo/example uses the following version of software tools from Microchip:

- MPLAB® X IDE v5.30
- XC8® Compiler v2.10
- MPLAB® Code Configurator (Plugin) v3.95
- MCC Core v4.85
- Microcontrollers and peripherals Library v1.80

# Demo Hardware Setup

- Plug the PIC16F18446 MCU into its socket on the Curiosity board
- Plug the IR Distance click into the mikroBUS slot of the Curiosity board
- Connect a set of headphones in series with 1k resistor to RC1 and GND

# MCC Settings

This section shows the settings used in the demo/example for various MCU modules configuration. These settings were done using the Microchip Code Configurator (MCC). Open MCC to look at the settings of the modules.

## System Module Settings

The MCU uses the high frequency internal oscillator (HFINTOSC), and the clock is set to 8 MHz. Watchdog Timer is not used in this demo, so it is disabled.

![System Module Settings](./images/2.png)

## ADCC Settings

ADCC is used to read the IR Distance sensor. It is configured to operate in basic mode, with a clock of Fosc/8.

![ADCC Settings](./images/3.png)

## NCO1 Settings

NCO1 is used to generate the square signal on a specific frequency. It is configured to operate in fixed duty cycle (FDC) mode, with output active high, and clock source Fosc.

![NCO Setting](./images/4.png)

## Pin Manager Settings

The pins are configured as follows:

- ADCC input on RC2, named channel_ANC2
- NCO1 output is connected to pin RC1
  ![NCO output](./images/5.png)
  ![Pin Manager](./images/6.png)

# Operation

1. After making the above hardware connections, connect the headphones in series with 1k resistor to RC1 and GND.
2. Connect the Curiosity board to PC using the USB cable.
3. Build demo firmware and load the generated hex file onto the PIC16F18446 MCU. When the demo firmware is loaded, a tone will be heard in the headphones.
4. Move your hand above the IR Distance sensor to hear the tone frequency changing.

# Conclusion

This example shows how easy it is to use the PIC16F18446 and MCC to read the IR Distance Click and generate a variable frequency tone.
