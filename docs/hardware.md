# Hardware

This page covers what the project documents (the capstone presentation and its script, the project's Google Drive notes and the parts spreadsheets) say about the machine. The spreadsheets were written for planning and purchasing, so they do not describe the finished build. Anything the sources leave unspecified is listed under [Not yet documented](#not-yet-documented).

![CAD render of Voron Vitalis](images/cad-render-front.jpg)

## Base machine

- **Platform:** a modified Voron 2.4 r2. The Voron 2.4 r2 build guide is in [`Documents/Assembly_Manual_2.4r2.pdf`](../Documents/Assembly_Manual_2.4r2.pdf). The Voron 2.4 uses CoreXY motion and a gantry carried by four Z drives (Z0 to Z3).
- **Frame:** aluminium extrusion. For the frame, motors, hardware and linear rails, the project links a [Voron 2 starter bundle (350 mm)](https://www.3dlabtech.ca/product/voron-2-starter-bundle-350mm/).
- **Levelling:** automatic quad gantry levelling (QGL).
- **Enclosure:** fully enclosed.
- **Interface:** a touchscreen on the front of the frame.
- **Printed parts:** ABS and glass-filled ABS.

| | |
|---|---|
| ![Frame and motion system](images/frame-and-motion-system.jpg) | ![Gantry and toolhead carriage](images/gantry-and-carriage.jpg) |
| Frame, gantry and bed before the panels were fitted (August 2025) | X gantry and toolhead carriage (August 2025) |

## Tool changer and toolheads

- **Tool changer:** toolheads dock and swap using the [Daksh Tool Changer V2](https://github.com/ankurv2k6/daksh-toolchanger-v2) mechanism. The project's toolhead design log sets the goal of a toolhead built on this mechanism with a custom-designed syringe holder.
- **Toolheads:** four independent toolheads, each able to hold a different bioink. A toolhead can also be swapped for a specialised tool, such as a UV- or laser-curing module (see [Planned](#planned)).
- **Tool change time:** about 40 seconds for a full tool change, according to the capstone presentation script.
- **Temperature control:** each toolhead has temperature-management hardware and a fan, so it can heat or cool its bioink.
- **Tool alignment:** toolheads are aligned automatically by an open-source, camera-based alignment tool for Klipper, named "Klipper Alignment Tool Using Machine Learning" in the project notes. The camera hardware comes from Ember Prototypes.

## Extrusion

Extrusion is pneumatic: compressed gas pushes bioink out of the syringe. The project chose pneumatic over motor-driven (plunger) extrusion for pressure control and for compatibility with viscous bioinks. The presentation's feature summary lists a pressure buffer tank.

## Bed

The bed is a 35 × 35 cm heated aluminium plate. The BOM sheet lists a MIC6 plate (14 × 14 in, 5/16 in thick) and a 300 × 300 mm, 650 W Keenovo silicone AC heater with a thermistor.

![Frame interior and bed](images/frame-interior-and-bed.jpg)

## Electronics

| Item | Detail |
|---|---|
| Controller | LDO Leviathan (STM32F446) running Klipper, with a Raspberry Pi 5 host and a Raspberry Pi Pico (RP2040) secondary MCU for the pressure transducer. The original plan used a BIGTREETECH Manta M8P V2.0 (STM32H723); see [firmware.md](firmware.md). |
| Camera | Tool-alignment camera hardware from Ember Prototypes. The presentation's feature summary lists a 1080p camera at 15 fps. |
| Network | Ethernet, listed in the presentation's feature summary. |

The tracking spreadsheet, which dates from 2024 planning, also lists:

- a BIGTREETECH CB2 compute board
- microSD cards for the controller board and for the "pi"
- a BIGTREETECH Eddy probe for bed levelling, with a BLTouch as the alternative
- a 600 W, 24 V Mean Well power supply

## Parts spreadsheets

- [**Voron_Vitalis Tracking**](https://docs.google.com/spreadsheets/d/188soFzGzhO4Uy-CefZMIBgignTyijYFp2OP5K6e-ZxM/edit?usp=sharing) is the cost tracker from October to December 2024, totalling $950.80. It covers LEDs for UV curing (listed at 365, 405, 450, 475 and 520 nm), the controller, the host, the probe, the power supply, motors, belts, rails and ABS/ASA filament. It reflects an earlier plan: it lists a Voron Trident frame and MGN7H rails, while the later project documents describe a Voron 2.4.
- **Voron Vitalis BOM** (March 2025) is a Voron 2.4-style parts list with "found" and "bought" columns. It covers fasteners, GT2 pulleys and belts, MGN9H and MGN12H rails, Misumi 2020 extrusions, panels, IGUS cable chains, the bed plate and heater, Mean Well LRS-200-24 and RS-25-5 supplies, an Omron G3A solid-state relay, and NEMA 17 and NEMA 14 motors.

## Reference designs in this repository

`References/` holds third-party designs kept for reference. The project documents do not say which of these parts are fitted to the printer.

- [`References/Replistruder V3/Tools/`](../References/Replistruder%20V3/Tools/) holds syringe-tool parts: a main body, a plunger holder and holders for Hamilton and BD syringes. The Replistruder 3 is a syringe extruder from Adam Feinberg's lab at Carnegie Mellon University.
- [`References/Replistruder V3/Calibration setup/`](../References/Replistruder%20V3/Calibration%20setup/) holds mounts and lids for a camera PCB and a Raspberry Pi.
- [`References/Replistruder V3/Modified Gregory Holloway's toolchanger enclosure/`](../References/Replistruder%20V3/Modified%20Gregory%20Holloway's%20toolchanger%20enclosure/) holds enclosure panels (top, side, rear and door) and printed parts, including a HEPA-filter and fan mount.
- [`References/Replistruder V4/`](../References/Replistruder%20V4/) holds the Replistruder 4 STEP files from Tashman, Shiwarski and Feinberg, *HardwareX* 9, e00170 (2021), [doi:10.1016/j.ohx.2020.e00170](https://doi.org/10.1016/j.ohx.2020.e00170). Those files are licensed CC BY-SA 4.0 by their authors.

## Planned

- **VitalSlicer:** a custom slicer under development. As of October 2025 it was expected to be completed in 2026. It will generate bioprinting G-code that accounts for bioink type, extrusion rate, tool changes and curing settings.
- **UV-curing toolhead:** a tool option the tool-changer design supports. Work on it was scheduled for September 2025, but the documents do not confirm a finished toolhead.
- **Laser-curing module:** named as a possible future tool module.

## Not yet documented

This repository and the project documents do not yet contain:

- the printer's own Klipper configuration, including the tool-changer docking macros and tool offsets
- the pneumatic system's parts and settings: valve, regulator, pressure sensing, operating pressures, and how extrusion commands map to pressure
- wiring diagrams
- build or calibration instructions
