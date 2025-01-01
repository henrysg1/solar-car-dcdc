# DC-DC Converter for Solar Car

![image](https://github.com/henrysg1/solar-car-dcdc/assets/115489513/1c586e69-ef92-4704-8230-66a5872dab1d)

## Overview

This repository contains the design files for a DC-DC converter used in the University of Nottingham's solar race car. The converter steps down the battery voltage from 135V to 12V, which is essential for powering various low-voltage components in the vehicle.

## Features

- **Input Voltage:** 135V
- **Output Voltage:** 12V
- **Output Current:** Up to 50A
- **Efficiency:** > 90%
- **Protection:** Overvoltage, Overcurrent, Thermal Shutdown
- **Compact PCB Design**

## Status

The PCB revision in this repository has been manufactured and succesfully tested and implemented in the solar car, verifying that the system works as intended.

## Getting Started

### Prerequisites

To work with the design files, you will need:

- [KiCad](https://kicad.org/) for schematic and PCB design. **Important Note: For this project, a Nightly Development Build of KiCAD has been used (6.99). The project will not work on a Stable Version release (6.00)**

### Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/dcdc-converter-solar-car.git
   cd dcdc-converter-solar-car
   ```
2. Include the component files in the KiCAD project (in the 'Component Files' folder)
3. Open the schematic file (dcdc_converter.sch) in KiCad.
4. Open the PCB layout file (dcdc_converter.kicad_pcb) in KiCad.

## Schematic

![image](https://github.com/henrysg1/solar-car-dcdc/assets/115489513/ccc3d81f-a005-4942-9a68-fbe2e8a8522a)

The schematic for the DC-DC converter is designed to step down the voltage from 135V to 12V. Here are the key sections and components:

### Input Section
- **J2, J3 (Connectors):** These connectors receive the high voltage (135V) input.
- **F1, F2 (5A Fuses):** Provide overcurrent protection for the high voltage input.

### Relay Control
- **K1 (Relay):** This relay enables or disables the DC-DC converter based on an external switch connected through IPL1.
- **D1 (Diode):** Acts as a flyback diode for the relay coil, protecting against voltage spikes.

### Primary Conversion Stage
- **L1, L2 (1µH Inductors):** Form LC filters along with C1 and C2 to smooth the input voltage.
- **R1, R2 (1Ω Resistors):** Used for current sensing in the primary stage.

### DC-DC Converter Modules
- **PS1, PS2 (DCM3623T5N13B4T00):** These modules handle the main conversion from high to low voltage. They include control and feedback components:
  - **R5, R6 (510Ω, 50kΩ Resistors)**
  - **RV1, RV2 (250kΩ Potentiometers)**
  - **D3, D4 (LTST-C193KRKT-5A Diodes)**

### Output Section
- **L3, L4 (0.15µH Inductors):** Further filter the output voltage.
- **C3, C4 (1000µF Capacitors):** Stabilize the output voltage.
- **F4, F5 (25A Fuses):** Provide overcurrent protection for the output.
- **J4 (Output Connector):** The connector for accessing the stepped-down 12V output.

This design ensures efficient voltage conversion with necessary protections for both input and output stages.

## PCB Layout

![image](https://github.com/henrysg1/solar-car-dcdc/assets/115489513/aa789400-9e2e-4e16-87a7-bc04545a233d)

The PCB layout is designed to maximise efficiency and handle high current traces. Key considerations include:

- Trace Widths: Sized appropriately for current handling.
- Component Placement: Optimised for thermal management and isolating voltages.
- Ground Plane: Ensures low impedance return paths.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Acknowledgments
University of Nottingham Solar Race Team \
KiCad Community
