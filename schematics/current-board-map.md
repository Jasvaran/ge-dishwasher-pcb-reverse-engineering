# Current Schematic Reconstruction

Legend:
- Solid connections below represent measured/confirmed continuity.
- `[TBD]` marks unknown function or voltage.
- This is an architecture-level reconstruction, not yet a complete production schematic.

```text
POWER ENTRY / TRANSFORMER

J1-1 -------- V1-1 -------- T1 bottom pin 3
                 |
              [ V1 ]
                 |
J1-3 -------- V1-2 -------- T1 bottom pin 4
  |
  +------------------------- V2 pad 2

J1-2 ----------------------- V2 pad 1

Transformer secondary / rectifier / rails: [TBD]


RELAY COIL CONTROL

              SHARED RELAY COIL RAIL [VOLTAGE TBD]
                    |    |    |    |    |
                   K1   K2   K3   K4   K5
                  pin3 pin3 pin3 pin3 pin3
                    |    |    |    |    |
                    +----+----+----+----+
                    |
                 D22 right

K1 pin5 --------------------------- U6 pin16
K2 pin5 --------------------------- U6 pin15
K3 pin5 --------------------------- U6 pin14
K4 pin5 --------------------------- U6 pin10
K5 pin5 --------------------------- U6 pin11

U6 pin9 --------------------------- D22 left

U6 = MC1413-family Darlington array
Individual coil paths are consistent with low-side switching.


RELAY CONTACT / LOAD SIDE

K1 pin2 --------------------------- J2 pin1
K2 pin2 --------------------------- J2 pin2
K3 pin2 --------------------------- J2 pins3-4

K1-K5 pin4 shared wide contact bus - J2 pins7-8
Bus electrical identity: [TBD]


LOGIC / PANEL AREA

U7 bottom-right -- R44 (1.001k) -- C23 left -- J7 fourth-from-bottom

LOGIC GROUND:
C23 right
  |
  +-- J7 first-from-bottom
  +-- C22 negative
  +-- C9 negative
  +-- U5 pin5 (93C86 GND)

C8 negative is NOT continuous with this logic-ground net.
```

## Next Schematic Targets

1. Trace the shared relay-coil rail back to its source.
2. Map T1 secondary pins.
3. Identify rectifier/filter components and establish DC rails.
4. Map U6 inputs to the controlling logic.
5. Complete J2 load mappings.
6. Identify U7 and map remaining J7/J8 signals.
