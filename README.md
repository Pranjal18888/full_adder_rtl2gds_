# Full Adder — RTL to GDS Flow (OpenLane + SkyWater Sky130 PDK)

This project implements a 1-bit Full Adder in Verilog and carries it through a complete open-source RTL-to-GDS physical design flow using OpenLane with the SkyWater Sky130 open-source PDK.

## Design

module full_adder (
    input  a,
    input  b,
    input  cin,
    output sum,
    output cout
);
    assign sum  = a ^ b ^ cin;
    assign cout = (a & b) | (b & cin) | (a & cin);
endmodule

## Tools Used

| Stage | Tool |
|---|---|
| Flow orchestration | OpenLane (Python-based CLI) |
| Logic synthesis | Yosys |
| Floorplan / Placement / CTS / Routing / STA | OpenROAD |
| DRC / LVS / GDS layout | Magic |
| Process Design Kit | SkyWater Sky130 (open-source) |

## Repository Structure

full_adder_rtl2gds/
- src/full_adder.v
- config.json
- RUN.md
- docs/flow_summary.md
- README.md

## Results

- DRC violations: 0
- LVS: clean
- Setup/Hold timing violations: 0
- Flow status: [SUCCESS]: Flow complete.

Final GDS-II layout generated at:
runs/<RUN_TAG>/results/final/gds/full_adder.gds

## What is RTL to GDS?

RTL-to-GDS is the process of converting a hardware description (Verilog RTL) into a fabrication-ready physical chip layout (GDS-II), passing through synthesis, floorplanning, placement, clock tree synthesis, routing, and signoff checks (DRC/LVS/STA).


