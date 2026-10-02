# Firmware

Voron Vitalis runs [Klipper](https://www.klipper3d.org/) on an LDO Leviathan mainboard (STM32F446) with a Raspberry Pi 5 host, and a Raspberry Pi Pico (RP2040) runs as a secondary Klipper MCU to read the pneumatic pressure transducer. The files in `Firmware/Manta M8P firmware/` come from the project's original controller plan, a BIGTREETECH Manta M8P V2.0 (STM32H723). This page describes those two files and what they do and do not contain.

## `Manta M8P V2.0 Firmware.cfg`

This file is identical to BIGTREETECH's generic sample configuration for the board, [`V2.0/Firmware/generic-bigtreetech-manta-m8p-V2_0.cfg`](https://github.com/bigtreetech/Manta-M8P/blob/master/V2.0/Firmware/generic-bigtreetech-manta-m8p-V2_0.cfg) in the [bigtreetech/Manta-M8P](https://github.com/bigtreetech/Manta-M8P) repository (SHA-256 `148d04dc542ef2643b9933caa26b98b8a12e2d651f494a4e18ce96f532d195c1`, compared in October 2026). It is a pin map with placeholder machine settings, not the configuration of this printer.

Its header states that Klipper must be built for the STM32H723 with a 128 KiB bootloader and a 25 MHz crystal, using USB (PA11/PA12), CAN (PD0/PD1) or serial (USART1, PA10/PA9).

### Active sections

| Section | Settings |
|---|---|
| `[stepper_x]`, `[stepper_y]` | Motor 1 and Motor 2; 16 microsteps; `rotation_distance: 40`; endstops `^PF4` and `^PF3`; travel 0 to 235 mm |
| `[stepper_z]` | Motor 3; 16 microsteps; `rotation_distance: 8`; endstop `^PF2`; travel -5 to 270 mm |
| `[extruder]` | Motor 5; heater HE0 (`PA0`); thermistor T0 (`PB0`, Generic 3950); PID Kp 22.2, Ki 1.08, Kd 114; 0 to 250 °C; `nozzle_diameter: 0.4`, `filament_diameter: 1.75`, `rotation_distance: 33.500` |
| `[heater_bed]` | Heater `PF5`; thermistor `PB1` (ATC Semitec 104GT-2); `control: watermark`; 0 to 130 °C |
| `[fan]` | Fan 0 (`PF7`) |
| `[mcu]` | `serial: /dev/serial/by-id/usb-Klipper_Klipper_firmware_12345-if00` (placeholder ID) |
| `[printer]` | `kinematics: cartesian`; `max_velocity: 300`; `max_accel: 3000`; `max_z_velocity: 5`; `max_z_accel: 100` |
| `[board_pins]` | Aliases for the EXP1 and EXP2 display headers |

### Commented-out sections

Motor 4 (`[stepper_]`), `[extruder1]` to `[extruder3]` (Motors 6 to 8, heaters HE1 to HE3, thermistors T1 to T3), filament switch sensors, all TMC2209 and TMC2130 driver sections, the host SoC fan, heater fans 1 to 6, ADXL345, BLTouch, proximity-switch probe, PS_ON output, NeoPixel and hall filament width sensor.

### Not in this file

None of the following machine-specific configuration is present:

- CoreXY kinematics and the Voron 2.4 four-motor Z axis
- quad gantry levelling and its probe
- the other three toolhead heaters and thermistors
- tool changer docking macros and tool offsets
- outputs for the pneumatic extrusion system
- tool-alignment camera configuration
- stepper driver (TMC) settings

## `Manta M8P V2 H723 bootloader.bin`

A 20,052-byte binary image. Its vector table (initial stack pointer `0x24000760`, reset handler `0x080002ED`) is linked to run from the start of internal flash at `0x08000000`, which is consistent with the bootloader that the 128 KiB application offset in the config header refers to.
