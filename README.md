# SCRAP engine
Alternative main board for the [Proto-panda](https://github.com/mockthebear/proto-panda) protogen head
Instead of driving the panels directly, it uses the [RP-HUB75](https://github.com/RoboticsBrno/RP-HUB75) as the translator.

<img src=imgs/thumbnail.png alt="main thumbnail" width="600"/>

Simplified design with only crucial features for running **SCRAP-OS** (Protogen firmware,Work In Progress)


## Features
- main MCU is the ESP32-S3 with 16MB of FLASH and 8MB of PSRAM
- the driver is connected over Quad SPI, which allows for high refresh rate draws
- Runs off 5V 3A power supply (actual consumption is often a lot less)
- Has a Addressable LED port
- Full 5V FAN header with PWM and tachometer support (best used with a Noctua NF-A4x10)
- I2C over the Qwiic port (3.3V tolerant only)
- Two ways of Boop sensor: either classic TTP223 capacitive sensor or (WIP) a distance sensor over I2C
- Integrates a microphone with manually adjusted gain (connected to an ADC channel of MCU)
- Has amazing art on the back by **@foxxerfelicity** ([IG](https://www.instagram.com/foxxerfelicity))!

*the back side of the PCB*

<img src=imgs/back.png alt="art on the back of PCB" width="600"/>

## Why?
The original board is great, but I didn't want to use the original firmware, with it SD card would've been not useful. And I didn't need some of the original features
That's why I made this board, it is only 2 layers, stripped down to only the things I need and uses the HUB75 driver I have laying around.

## Schematic
Full PDF of the schematic [here](pcb/SCRAP-engine-SCHEM-final.pdf)

<img src=imgs/schematic.png alt="entire schematic" width="600"/>

## PCB

Full PDF of the PCB design [here](pcb/SCRAP-engine-PCB-final.pdf)

<img src=imgs/PCB-top.png alt="top layer" width="600"/>

<img src=imgs/PCB-bottom.png alt="bottom layer" width="600"/>

## Firmware

Firmware called **SCRAP-OS** will be worked on, but at the moment doesn't exist.

## Credits + extra

I have used the "Shentox" font for all markings, which is free for personal use

Then I used font "Chewy" from Googlefonts

I have got inspiration from the project [Proto-panda](https://github.com/mockthebear/proto-panda).

And I have looked at inspiration during wiring the display port from [Saturn](https://github.com/RoboticsBrno/Saturn).
