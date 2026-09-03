# Power Supply Analysis

> Work in progress. This file records only measured power-area connectivity and clearly marks interpretation separately.

## Confirmed J1 / V1 / T1 Connectivity

Component-side J1 numbering:

| Net | Confirmed Connections |
|---|---|
| NET A | J1 pin 1 <-> V1 pin 1 <-> T1 bottom-row pin 3 |
| NET B | J1 pin 3 <-> V1 pin 2 <-> T1 bottom-row pin 4 <-> V2 pad 2 |
| V2 branch | J1 pin 2 <-> V2 pad 1 |

## Interpretation

T1 is located in the board's power section and the above measurements establish its input-side connectivity to J1.

V1 is physically a green disc component connected between the two J1/T1 nets. Its location and topology are consistent with an input protection component, but the exact device identity should remain provisional until its marking/specification is confirmed.

V2 is unpopulated. One pad connects to J1 pin 2 and the other connects to NET B.

## Not Yet Mapped

- Transformer secondary pins and secondary voltage
- Rectifier topology
- Filter capacitors associated with each low-voltage rail
- Logic supply voltage(s)
- Relay-coil supply source and voltage
- Relationship between relay supply and transformer secondary
- J1 pin functional names

Do not infer AC Line/Neutral assignments or relay supply voltage solely from physical trace width or component placement.
