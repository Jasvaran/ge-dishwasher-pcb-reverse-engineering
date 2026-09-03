# Continuity and Resistance Measurements

> Measurements were taken with the board unpowered. Conformal coating was locally cleared where necessary to obtain reliable probe contact.

## Relay Coils

| Test | Result |
|---|---:|
| K1 pin 5 <-> pin 3 | ~403 ohm |
| K2 pin 5 <-> pin 3 | ~399-403 ohm |
| K3 pin 5 <-> pin 3 | ~399-403 ohm |
| K4 pin 5 <-> pin 3 | ~399-403 ohm |
| K5 pin 5 <-> pin 3 | ~399-403 ohm |
| K1-K5 pin 3 common net | Continuity confirmed |

## Relay Driver

| Test | Result |
|---|---|
| K1 pin 5 <-> U6 pin 16 | Continuity |
| K2 pin 5 <-> U6 pin 15 | Continuity |
| K3 pin 5 <-> U6 pin 14 | Continuity |
| K4 pin 5 <-> U6 pin 10 | Continuity |
| K5 pin 5 <-> U6 pin 11 | Continuity |
| Relay coil common <-> D22 right | 0 ohm |
| U6 pin 9 <-> D22 left | 0 ohm |
| K1 pin 3 -> D22 left | ~15-16 Mohm |
| U6 pin 9 -> D22 right | OL |
| D22 forward diode mode | ~0.670 V |
| D22 reverse diode mode | OL |

## Relay Contacts / J2

| Test | Result |
|---|---|
| K1 pin 2 <-> J2 pin 1 | Continuity |
| K2 pin 2 <-> J2 pin 2 | Continuity |
| K3 pin 2 <-> J2 pins 3 and 4 | Continuity |
| Shared K1-K5 pin-4 wide bus <-> J2 pins 7 and 8 | Continuity |

## Logic Area

| Test | Result |
|---|---:|
| R44 across pads | 1.001 kOhm |
| R44 right <-> C23 left <-> J7 fourth-from-bottom | ~0.1 ohm |
| U7 bottom-right <-> R44 left | ~0.1 ohm |
| C23 right <-> J7 first-from-bottom | ~0.1 ohm |
| Logic ground <-> C22 negative | Continuity |
| Logic ground <-> C9 negative | Continuity |
| U5 pin 5 <-> C22 negative | Continuity |
| C22 negative <-> C8 negative | OL / no continuity |

## Control Panel Tests

With panel connected:
- J7 first-from-bottom (logic ground) to J7 second-from-bottom: ~7.42 kOhm.
- No observed resistance change while pressing buttons.

Panel disconnected:
- Panel connector has 20 physical contacts.
- Contact 1-from-bottom to all others: OL; no button-induced change.
- Contact 2-from-bottom to contact 3-from-bottom: ~12.12 kOhm; no button-induced change.
- No tested pair produced a clear button-induced continuity/resistance change.

These results do not support treating the panel as a simple one-common mechanical switch matrix based on the measurements performed so far.
