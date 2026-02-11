# CD4001B – CMOS Quad 2-Input NOR Gate (Transistor-Level Layout)

This repository contains a transistor-level CMOS implementation of the CD4001B, a quad
2-input NOR gate in CMOS TSMC 180 nm 1P6M 1.8V technology, developed as part of a university course in integrated circuit and system
design.

<p float="left">
  <img src="https://github.com/user-attachments/assets/1c1ed2d1-ce41-47d8-a289-76af6298b184" width="45%" />
  <img src="https://github.com/user-attachments/assets/240d893d-c80b-4738-9348-b736262c7727" width="45%" />
</p>

Project covers the complete design flow of a simple digital integrated circuit, including
schematic design, physical layout, and post-layout circuit extraction, using Magic VLSI.

---

## Project Description

The CD4001B gate was implemented at the transistor level using complementary NMOS and
PMOS devices. The design follows the functional structure of the original CD4001B CMOS
logic gate and includes:

- Transistor-level realization of a 2-input NOR gate
- Replication of the gate to form a quad-gate structure
- Manual full-custom layout of the circuit
- Power and ground routing consistent with CMOS design practices
- I/O connections defined at the layout level

---

## Design Flow

The project was carried out according to the following steps:

1. Analysis of the CD4001B logic function and transistor-level schematic
2. Creation of a CMOS schematic using NMOS and PMOS transistor networks
3. Manual layout of the circuit in Magic VLSI
4. Layout organization with respect to power distribution and signal routing
5. Design Rule Check (DRC) verification
6. SPICE netlist extraction from the completed layout
7. Functional verification of the extracted circuit

---
## Pre-Layout Simulations in LTspice

<p float="left">
  <img src="https://github.com/user-attachments/assets/1fc53e88-b91f-468b-81a5-ce121c719d44" width="45%" />
  <img src="https://github.com/user-attachments/assets/09782381-ac98-439e-817b-9a6566eb8911" width="45%" />
</p>

Gate and 4 stage buffer schematics in LTspice

<img width="754" height="1176" alt="image" src="https://github.com/user-attachments/assets/cb09630e-197c-40cd-8c30-0a7030ef26ae" />

Spice Netlist

All simulations are in the presentation document in Documentation tab. The presentation also includes comparison of pre-layout and post-layout extraction of characteristics.

---
## Layout Characteristics

<img width="1115" height="1165" alt="Layout" src="https://github.com/user-attachments/assets/6125bee6-4fcf-4aef-a923-c9bb342b2dce" />

- Fully custom transistor placement and routing
- Explicit separation of NMOS and PMOS regions
- Shared diffusion where possible to reduce area
- Dedicated VDD and VSS routing
- Layout structured to allow replication of identical logic cells

Screenshots included in the repository show:
- The complete quad-gate layout
- Individual gate layout
- Correspondence between schematic-level and layout-level implementations

---

## ESD Protection

The design includes **input/output ESD protection structures** implemented directly at
the layout level. The protection is based on **diode-connected diffusion structures**
between the I/O pad and the power rails.

<img width="1055" height="1163" alt="ESD_Protection" src="https://github.com/user-attachments/assets/23b444a7-ec3e-4dca-8061-d15f4483d0ea" />

### ESD Structure Description

Each protected signal pad is connected to:
- a diode to **VDD**, and
- a diode to **VSS**,

forming a standard CMOS diode-based ESD protection network. The diodes are realized
using diffusion regions and well/substrate junctions consistent with CMOS layout
practices.

During an ESD event:
- positive voltage spikes are clamped to VDD,
- negative voltage spikes are clamped to VSS,

thereby limiting the voltage stress applied to the internal core circuitry.
## Tools and Technologies

- Magic VLSI – layout editor and extraction tool
- CMOS technology assumptions consistent with educational design rules
- SPICE – simulation of extracted netlists

---

## Notes

This project was developed for educational purposes as part of a university laboratory
course. The layout is not optimized for silicon area, speed, or power consumption and is not
intended for fabrication without further process-specific adaptation.
