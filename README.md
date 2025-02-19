# YuChen BioPrinter

**Link to Main Spreadsheets**
[Google Sheets](https://docs.google.com/spreadsheets/d/188soFzGzhO4Uy-CefZMIBgignTyijYFp2OP5K6e-ZxM/edit?usp=sharing)

## Overview

This project is a customized **BioPrinter** built on the **Voron 0.2** 3D printer platform. It is designed to perform bio-fabrication tasks such as printing biological materials or tissues. Leveraging the precision and reliability of the Voron design, this bio-printer offers a robust platform for a wide range of bio-printing applications.

## Features

- **High Precision Printing**: The Voron platform ensures accurate, repeatable results with tight tolerances.
- **Sterilizable Build Plate**: The build plate is modified to allow easy sterilization between prints to maintain a sterile environment.
- **Climate Control**: Added control system to maintain an optimal temperature and humidity level in the print chamber.
- **Easy Material Loading**: The system has been optimized for fast and sterile material loading, ensuring minimal contamination risks.

## Bill of Materials (BOM)

For a complete list of components required to build this BioPrinter, refer to the Bill of Materials available in this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/188soFzGzhO4Uy-CefZMIBgignTyijYFp2OP5K6e-ZxM/edit?usp=sharing).

The BOM includes:
- **Customized Voron Trident Frame**: Custom Voron Design Frame
- **Voron 0.2 Z-Axis Assembly**: Voron 0.2 Z-Axis Assembly
- **Custom Bio-Compatible Nozzle**: Designed to handle bio-materials
- **Climate Control Components**: Sensors, fans, and other components to maintain a controlled printing environment
- **Electronics**: Microcontroller, stepper motors, and wiring for controlling the printer
- **Build Plate and Sterilization System**: Removable build plate for easy sterilization
- **UV toolhead**: UV light toolhead to cure print
[BOM Sheet](https://docs.google.com/spreadsheets/d/188soFzGzhO4Uy-CefZMIBgignTyijYFp2OP5K6e-ZxM/edit?usp=sharing)
  
## Requirements

- **Voron 0.2 Kit**: Base frame and motion system of the BioPrinter.
- **Custom Nozzle**: A nozzle designed for bio-compatible printing.
- **Sterile Environment**: The printer should operate in a controlled and clean environment for bio-printing.
- **Control Software**: Adapted firmware to control the new functionalities (climate control, sterilization cycles).

## Setup Instructions

1. **Design the Frame First**: Deign it first

## Usage

1. **Prepare the Material**: Load your bio-material (e.g., hydrogels, cell-laden inks) into the extruder using sterile techniques.
2. **Calibrate the Printer**: Run the calibration procedure to ensure accurate prints.
3. **Start Printing**: Use the appropriate G-code for your bio-printing task, ensuring the proper climate control settings are enabled.
4. **Post-Print**: Sterilize the build plate and nozzle after each print to maintain a clean printing environment.

## References

**Daksh Tool Changer V2**
[Daksh Toolchanger github](https://github.com/ankurv2k6/daksh-toolchanger-v2)

**Open Source Scientific Report**

[Open Source Bioprinter by Adam Engberg](https://www.nature.com/articles/s41598-021-00931-1)

[Voron 2.4 Frame/motors/hardware/linear rails](https://www.3dlabtech.ca/product/voron-2-starter-bundle-350mm/)

## Supporters

- **Proundly supported by LDO Motors
