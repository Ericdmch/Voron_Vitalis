# BioPrinter based on Voron 0.2

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

1. **Build the Voron 0.2 Frame**: Follow the official Voron 0.2 assembly guide to complete the printer frame and motion system.
2. **Install Bio-Compatible Nozzle**: Replace the standard nozzle with the custom bio-printing nozzle.
3. **Sterilization Preparation**: Ensure the build plate is set up for easy removal and sterilization between prints.
4. **Set Up Climate Control**: Install the climate control system to regulate temperature and humidity in the print chamber.
5. **Install Firmware**: Upload the modified firmware for bio-printing to the controller board.

## Usage

1. **Prepare the Material**: Load your bio-material (e.g., hydrogels, cell-laden inks) into the extruder using sterile techniques.
2. **Calibrate the Printer**: Run the calibration procedure to ensure accurate prints.
3. **Start Printing**: Use the appropriate G-code for your bio-printing task, ensuring the proper climate control settings are enabled.
4. **Post-Print**: Sterilize the build plate and nozzle after each print to maintain a clean printing environment.

## Troubleshooting

- **Inconsistent Print Quality**: Recalibrate the nozzle and ensure the material is flowing smoothly without clogs.
- **Temperature Fluctuations**: Check the climate control system to make sure the set temperature and humidity levels are maintained.
- **Sterilization Issues**: Verify that the sterilization process is complete and that all surfaces have been properly cleaned.

## License

This project is open-source and licensed under the [MIT License](https://opensource.org/licenses/MIT).