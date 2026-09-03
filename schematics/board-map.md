# Board Map

> Status: Work in progress. This document separates measured connections from hypotheses.

## Identified Components

- **U6:** MC1413-family 7-channel Darlington transistor array used in the relay-driver section.
- **U5:** Atmel 93C86 EEPROM.
- **T1:** Laminated-core transformer in the power section.
- **V1:** Green disc component located across the J1/T1 input nets, consistent with a protection device. Exact part marking/function should be confirmed before assigning a final schematic symbol.
- **V2:** Unpopulated two-pad footprint associated with J1 pin 2 and the J1 pin 3 / T1 net.
- **J1:** 3-pin connector in the power-entry area.
- **J2:** Multi-pin connector adjacent to the relay/load section. Board labels include CIRC PUMP, WATER VALVE, HEATER, and AUX PUMP.
- **J7:** Control-panel ribbon connector.
- **J8:** Display-related ribbon connector.

## Confirmed Logic-Area Nets

### NET 001
- R44 right pad
- C23 left pad
- J7 fourth physical pin from bottom

Measured continuity: approximately 0.1 ohm.

### NET 002
- U7 bottom-right physical pin
- R44 left pad

Measured continuity: approximately 0.1 ohm.

R44 measures approximately 1.001 kOhm across its pads.

### NET 003: Logic Ground
Confirmed continuity between:
- C23 right pad
- associated via
- J7 first physical pin from bottom
- C22 negative
- C9 negative
- U5 pin 5

Negative result:
- C22 negative is **not** continuous with C8 negative.

## Power-Area Nets

All J1 references are from the component side.

### NET A
- J1 pin 1
- V1 pin 1
- T1 bottom-row pin 3

### NET B
- J1 pin 3
- V1 pin 2
- T1 bottom-row pin 4
- V2 pad 2

### Additional V2 Connection
- J1 pin 2
- V2 pad 1

## Relay / Load Section

Relay terminal numbering is standardized to the **back / solder-side view**:

```text
      4
  5       3
  1       2
```

Confirmed relay contact/load mappings:
- K1 pin 2 <-> J2 pin 1
- K2 pin 2 <-> J2 pin 2
- K3 pin 2 <-> J2 pins 3 and 4
- Shared wide relay pin-4 contact bus <-> J2 pins 7 and 8

The electrical identity of the shared pin-4 bus is still TBD. Do not label it Line or Neutral yet.

## Open Questions

- Relay-coil supply voltage and source
- Exact system role of D22
- Transformer secondary, rectification, filtering, and low-voltage rails
- Exact electrical identity of the relay pin-4 contact bus
- U7 identity/function
- J7/J8 signaling architecture
- Remaining J2 load-to-relay mappings
