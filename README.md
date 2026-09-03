# General Electric Dishwasher Control PCB Reverse Engineering

> Work in progress

Reverse engineering of a production General Electric dishwasher
control PCB to develop practical experience with PCBA diagnostics,
schematic reconstruction, component identification, and systematic
electrical troubleshooting.

The goal is to reconstruct the electrical architecture of the board
from the physical PCB while documenting the diagnostic process used
to identify nets, components, interfaces, and functional subsystems.

## Current Progress

So far I have:

- Identified major board components and functional regions
- Identified the MC1413 Darlington transistor array used for relay control
- Identified the Atmel 93C86 EEPROM
- Mapped individual relay coil connections to MC1413 output channels
- Identified a shared relay coil supply net
- Traced portions of the transformer and input protection circuitry
- Established a confirmed logic ground net
- Traced several control-panel connector signals
- Begun reconstructing the board schematic from continuity measurements

## Methodology

The board is reverse engineered primarily through:

1. Visual PCB inspection
2. Component marking identification
3. Datasheet research
4. Resistance and continuity measurements
5. PCB trace inspection
6. Net documentation
7. Functional subsystem identification
8. Schematic reconstruction

Measurements are recorded as confirmed connections before being
incorporated into the reconstructed schematic.

## Tools

- Digital multimeter
- Component datasheets
- Magnification
- PCB photography
- Schematic capture software

## Current Architecture

Major subsystems currently being investigated include:

- AC power input and protection
- Transformer / low-voltage power supply
- Relay output stage
- MC1413 Darlington relay driver
- EEPROM / logic circuitry
- Control-panel interface
- Load connectors

## Project Goals

- Reconstruct a reproducible schematic of mapped portions of the PCB
- Identify power, control, and load paths
- Understand the interface between logic circuitry and high-current loads
- Document a repeatable PCB reverse-engineering workflow
- Eventually investigate control signals using appropriate test equipment

## Status

Active project. Findings and schematics are updated as additional nets
are confirmed.


## Control Logic Architecture:

                    CONTROL LOGIC
                         │
                         │ control signals
                         ▼
                  ┌─────────────┐
                  │    U6       │
                  │   MC1413    │
                  │ Darlington  │
                  │   Array     │
                  └──────┬──────┘
                         │
                 individual sinks
                 │   │   │   │   │
                 ▼   ▼   ▼   ▼   ▼
                K1  K2  K3  K4  K5
                 │   │   │   │   │
                 └───┴───┴───┴───┘
                         │
                     LOAD OUTPUTS
                         │
                         ▼
                        J2
