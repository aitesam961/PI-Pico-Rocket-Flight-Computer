# Raspberry Pi Pico Rocket Flight Computer

A Raspberry Pi Pico-based flight-computer board design combining battery power, navigation, motion and pressure sensing, radio connectivity, and storage interfaces.

This repository contains the hardware design, manufacturing exports, and mechanical files. Flight software and sensor drivers are not included.

<p align="center">
  <img width="400" src="images/Screenshot%202022-02-26%20103118.png" alt="Flight computer board render">
  <img width="400" src="images/Screenshot%202022-02-26%20103131.png" alt="Flight computer board side view">
  <img width="400" src="images/Screenshot%202022-02-26%20103152.png" alt="Flight computer board alternate view">
</p>

## Features and module interfaces

| Component | Intended role |
| --- | --- |
| Raspberry Pi Pico / RP2040 | Main microcontroller |
| 3.7 V LiPo power section | Battery supply with onboard charging and management circuitry |
| NEO-6M GPS module | Position information |
| Ai-Thinker Ra-02 / SX1278 LoRa module | Radio link |
| BMP280 | Pressure sensing |
| MPU6050 | Accelerometer and gyroscope measurements |
| SD card module | Data storage |
| GPIO header | External peripherals |

The design uses module footprints to simplify assembly. The original project allows unused modules to be omitted; firmware and wiring must match the modules actually fitted. A charging indicator LED is also included.

## Form factor and power

<p align="center">
  <img width="400" src="images/Screenshot%202022-02-26%20103259.png" alt="Board dimensions and mounting layout">
  <img width="400" src="images/Screenshot%202022-02-26%20103315.png" alt="Board mechanical view">
</p>

The original design documentation lists:

| Parameter | Value |
| --- | --- |
| Board dimensions | 90 × 90 mm |
| Mounting | Four 2 mm screw mounts |
| Signal layers | 2 |
| Battery | 3.7 V nominal LiPo, up to 4.2 V charged |
| Battery capacity | 1–5 Ah |
| Charging current | 500 mA |

Use the PCB and mechanical files to check dimensions, mounting clearances, and the power configuration for your build.

## Repository guide

Some exported filenames retain the older `Pico Breakout` label.

| Location | Contents |
| --- | --- |
| [EasyEDA_Source_files](EasyEDA_Source_files/) | Editable schematic and PCB JSON files |
| [manufacturing_files](manufacturing_files/) | Gerber archive, bill of materials, and pick-and-place CSV |
| [MCAD Files](MCAD%20Files/) | OBJ model archive and DXF drawing |
| [images](images/) | Board renders, layout views, and dimensional references |

## Getting started

1. Open the schematic and PCB JSON files in EasyEDA using its workflow for EasyEDA source files.
2. Trace the Pico-to-module connections and record the pin assignments for your firmware.
3. Review the BOM against the exact modules and connectors you plan to install.
4. Check the mechanical files against the intended enclosure and mounting arrangement.
5. After changing the design, regenerate the manufacturing files from the updated PCB.

Application development must provide sensor acquisition, radio communication, storage, and any required flight-computer behavior. The hardware files alone do not establish a complete or flight-tested system.

## Contributing

Contributions can include pin-mapping documentation, firmware examples, assembly notes, and measured hardware results. Include the board revision, fitted modules, and test conditions so others can reproduce the work.

## License

GNU General Public License v3.0. See [LICENSE.txt](LICENSE.txt) for the license text.
