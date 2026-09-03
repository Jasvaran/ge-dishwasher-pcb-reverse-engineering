# Relay Driver Analysis

## Purpose

Document the measured relationship between relay coils and U6, the MC1413-family Darlington transistor array.

The MC1413 is a seven-channel NPN Darlington driver intended for loads such as relays. The manufacturer pinout places outputs on pins 10-16, ground on pin 8, and the common suppression-diode connection on pin 9.

## Relay Orientation

All relay terminal numbers in this project use the **back / solder-side view**:

```text
      4
  5       3
  1       2
```

## Coil Identification

Resistance measurements identify relay pins **5 and 3** as the coil terminals.

| Relay | Coil Terminals | Measured Resistance |
|---|---|---:|
| K1 | 5 <-> 3 | ~403 ohm |
| K2 | 5 <-> 3 | ~399-403 ohm |
| K3 | 5 <-> 3 | ~399-403 ohm |
| K4 | 5 <-> 3 | ~399-403 ohm |
| K5 | 5 <-> 3 | ~399-403 ohm |

Relay pin 3 is a shared common net across K1-K5.

## Confirmed U6 Output Mapping

| Relay | Coil Terminal | U6 Pin |
|---|---|---:|
| K1 | pin 5 | 16 |
| K2 | pin 5 | 15 |
| K3 | pin 5 | 14 |
| K4 | pin 5 | 10 |
| K5 | pin 5 | 11 |

This measured topology is consistent with individual low-side relay control through U6.

## D22 Measurements

Confirmed:
- Relay coil common <-> D22 right pad: 0 ohm
- U6 pin 9 <-> D22 left pad: 0 ohm
- K1 pin 3 -> D22 left pad: approximately 15-16 Mohm
- U6 pin 9 -> D22 right pad: OL
- D22 diode-mode forward reading: approximately 0.670 V
- Reverse direction: OL

These measurements are recorded without assigning D22 a final system-level function yet.

## Current Interpretation

The measured board topology supports:
- one shared relay-coil rail at relay pin 3,
- individually controlled opposite coil terminals at relay pin 5,
- U6 outputs sinking the individual coils.

**Important:** The voltage of the shared coil rail has not yet been measured or traced to its source. It must not be labeled +12 V or any other voltage until confirmed.
