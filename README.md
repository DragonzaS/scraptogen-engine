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
The original board is great, but I didn't want to use the original firmware, with it SD card would've been not useful. And I didn't need some of the original features.
That's why I made this board, it is only 2 layers, stripped down to only the things I need and uses the HUB75 driver I have laying around.

## Schematic
Full PDF of the schematic [here](pcb/SCRAP-engine-SCHEM-final.pdf)

<img src=imgs/schematic.png alt="entire schematic" width="600"/>

## PCB

Full PDF of the PCB design [here](pcb/SCRAP-engine-PCB-final.pdf)

<img src=imgs/PCB-top.png alt="top layer" width="600"/>

<img src=imgs/PCB-bottom.png alt="bottom layer" width="600"/>

## Bill of Material
Full BOM [here]([pcb/BOM-final.ods](https://github.com/DragonzaS/scraptogen-engine/tree/main/pcb))(link to the pcb folder)

| Designator                    | Quantity | Supplier Part | Footprint                                | Value                            | link                  | Price                  |
|-------------------------------|----------|---------------|------------------------------------------|----------------------------------|-----------------------|------------------------|
| C1,C5,C9                      | 3        | C15849        | C0603                                    | 1uF                              | [link](https://jlcpcb.com/partdetail/C15849)                      | $0.03                  |
| C2                            | 1        | C57112        | C0603                                    | 10nF                             | [link](https://jlcpcb.com/partdetail/C57112)                      | $0.01                  |
| C3                            | 1        | C14858        | C0603                                    | 100pF                            | [link](https://jlcpcb.com/partdetail/C14858)                      | $0.01                  |
| C4,C6,C7,C11,C16,C18,C19      | 7        | C96446        | C0603                                    | 10uF                             | [link](https://jlcpcb.com/partdetail/C96446)                      | $0.07                  |
| C8,C10,C15,C20                | 4        | C14663        | C0603                                    | 100nF                            | [link](https://jlcpcb.com/partdetail/C14663)                      | $0.04                  |
| L1,L2,L3                      | 3        | C14709        | L0603                                    | BLM18PG121SN1D                   | [link](https://jlcpcb.com/partdetail/C14709)                      | $0.03                  |
| LED1                          | 1        | C2286         | LED-SMD_L1.6-W0.8-R-RD                   | KT-0603R                         | [link](https://jlcpcb.com/partdetail/C2286)                      | $0.01                  |
| R1,R2,R3,R15,R23,R24,R25,R26  | 8        | C25804        | R0603                                    | 10kΩ                             | [link](https://jlcpcb.com/partdetail/C25804)                      | $0.08                  |
| R4,R5,R6,R7,R8,R9,R10,R11,R12 | 9        | C22775        | R0603                                    | 100Ω                             | [link](https://jlcpcb.com/partdetail/C22775)                      | $0.09                  |
| R13,R14,R16                   | 3        | C23186        | R0603                                    | 5.1kΩ                            | [link](https://jlcpcb.com/partdetail/C23186)                      | $0.03                  |
| R17,R18                       | 2        | C22935        | R0603                                    | 1MΩ                              | [link](https://jlcpcb.com/partdetail/C22935)                      | $0.02                  |
| R19                           | 1        | C48997895     | RES-ADJ-SMD_JER33X-1-14                  | 100kΩ                            | [link](https://jlcpcb.com/partdetail/C48997895)                      | $0.10                  |
| R20                           | 1        | C31850        | R0603                                    | 22kΩ                             | [link](https://jlcpcb.com/partdetail/C31850)                      | $0.01                  |
| R21,R27,R28                   | 3        | C21190        | R0603                                    | 1kΩ                              | [link](https://jlcpcb.com/partdetail/C21190)                      | $0.01                  |
| R22                           | 1        | C23138        | R0603                                    | 330Ω                             | [link](https://jlcpcb.com/partdetail/C23138)                      | $0.01                  |
| SW1,SW2                       | 2        | C720477       | SW-SMD_L3.9-W3.0-P4.45                   | TS-1088-AR02016                  | [link](https://jlcpcb.com/partdetail/C720477)                      | $0.10                  |
| U1                            | 1        | C2913202      | WIRELM-SMD_ESP32-S3-WROOM-1              | 2.4GHz                           | [link](https://jlcpcb.com/partdetail/C2913202) [local link](https://www.gme.cz/v/1495911/al-goodwell-oa67pf583c2per-elektretovy-mikrofon)                      | $5.35(local $6.3)      |
| U2                            | 1        | C5343095      | CONN-SMD_10P-P2.50_HANXIA_HX-2.54-10P-WT | HX 2.54-10P WT                   | [link](https://jlcpcb.com/partdetail/C5343095)                      | $0.10                  |
| U3                            | 1        | C7430446      | CONN-SMD_4P-P1.00_MEGASTAR_ZX-SH1.0-4PWT | ZX-SH1.0-4PWT                    | [link](https://jlcpcb.com/partdetail/C7430446)                      | $0.07                  |
| U4,U5                         | 2        | C20615817     | SOD-523_L1.2-W0.8-LS1.6-BI               | H3V3LD5B                         | [link](https://jlcpcb.com/partdetail/C20615817)                      | $0.04                  |
| U6                            | 1        | C7456762      | SC-70-5_L2.0-W1.3-P0.65-LS2.1-BR         | MAX4466EXK+T                     | [link](https://jlcpcb.com/partdetail/C7456762)                      | $1.06                  |
| U8                            | 1        | C51118        | SOT-25-5_L2.9-W1.6-P0.95-LS2.8-BL        | AP2112K-3.3TRG1                  | [link](https://jlcpcb.com/partdetail/C51118)                      | $0.17                  |
| USB1                          | 1        | C5440757      | USB-C-SMD_HANELECTRICITY_161N-4XVS11     | 161N-4PVS11                      | [link](https://jlcpcb.com/partdetail/C5440757)                      | $0.06                  |
| H5                            | 1        |               | ELECTRET MICROPHONE                      | AL GOODWELL OA67PF583C2PER       | [local link](https://www.gme.cz/v/1495911/al-goodwell-oa67pf583c2per-elektretovy-mikrofon)                      | $0.69                |

### Cost for the PCB & PCBA:
screenshot from JLCPCB, doesn't include taxes and shipping

<img src=imgs/jlc-price.png alt="JLCPCB screenshot" width="600"/>

Costs (As of November 9th, 2026):

$37.54 (the PCB) + $ 6.89 (ESP32 module and microphone)

**Total cost: $44.43**

Plus taxes and shipping (for me that comes out at around extra $29 + $1.5 for in store pick up of the components).
Total cost for me will be around $75.
## Firmware

Firmware called **SCRAP-OS** is being worked on, at the moment it is untested code, should show basic expression on the displays.

## Credits + extra

I have used the "Shentox" font for all markings, which is free for personal use

Then I used font "Chewy" from Googlefonts

I have got inspiration from the project [Proto-panda](https://github.com/mockthebear/proto-panda).

And I have looked at inspiration during wiring of the display port from [Saturn](https://github.com/RoboticsBrno/Saturn).

And of course I thank again @FoxxerFelicity for giving me line art version of my protogen and their sona ^_^
