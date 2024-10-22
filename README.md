# YuChen BioPrinter

## Overview

This project is a customized **BioPrinter** built on the **Voron 0.2** 3D printer platform. It is designed to perform bio-fabrication tasks such as printing biological materials or tissues. Leveraging the precision and reliability of the Voron design, this bio-printer offers a robust platform for a wide range of bio-printing applications.

## Features

- **High Precision Printing**: The Voron 0.2 platform ensures accurate, repeatable results with tight tolerances.
- **Custom Nozzle for Bio-Materials**: Specially designed nozzle for handling bio-materials such as hydrogels and cell-laden inks.
- **Sterilizable Build Plate**: The build plate is modified to allow easy sterilization between prints to maintain a sterile environment.
- **Climate Control**: Added control system to maintain an optimal temperature and humidity level in the print chamber.
- **Easy Material Loading**: The system has been optimized for fast and sterile material loading, ensuring minimal contamination risks.

## Bill of Materials (BOM)

For a complete list of components required to build this BioPrinter, refer to the Bill of Materials available in this [Google Spreadsheet](https://docs.google.com/spreadsheets/d/188soFzGzhO4Uy-CefZMIBgignTyijYFp2OP5K6e-ZxM/edit?usp=sharing).

The BOM includes:
- **Voron 0.2 Frame Kit**: All mechanical parts for the Voron 0.2.
- **Custom Bio-Compatible Nozzle**: Designed to handle bio-materials.
- **Climate Control Components**: Sensors, fans, and other components to maintain a controlled printing environment.
- **Electronics**: Microcontroller, stepper motors, and wiring for controlling the printer.
- **Build Plate and Sterilization System**: Removable build plate for easy sterilization.
  
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

**Useful Links**

*Voron 0.2 References*

[Voron 0.2 Github](https://github.com/VoronDesign/Voron-0)
[Voron Design 0.2](https://vorondesign.com/voron0.2)
[Voron 0.2 Manual](https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/Manuals/VORON_V0.2r1_Assembly_Manual.pdf)