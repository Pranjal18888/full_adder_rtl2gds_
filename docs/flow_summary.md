# RTL-to-GDS Flow Summary — Full Adder

## 1. RTL Design
A 1-bit combinational full adder written in Verilog. No clock port since the design is purely combinational.

## 2. Synthesis
Yosys converts the Verilog RTL into a gate-level netlist mapped to the Sky130 standard cell library (sky130_fd_sc_hd).

## 3. Floorplanning & Placement
Die area and core utilization defined in config.json. Standard cells placed within the floorplan using OpenROAD.

## 4. Clock Tree Synthesis (CTS)
Skipped — not applicable since design is purely combinational.

## 5. Routing
OpenROAD's global and detailed router connects all nets using Sky130 metal layers, following Sky130 design rules.

## 6. Signoff Checks
- DRC (Magic) — 0 violations
- LVS — clean
- STA — 0 setup/hold violations at typical corner
- Antenna & ERC checks — passed

## 7. Output
Final GDS-II file (full_adder.gds) generated at:
runs/<RUN_TAG>/results/final/gds/full_adder.gds

## Notes
- Core area was small relative to default power grid settings — OpenLane automatically scaled the power grid down.
- A few standard library cells (tap, decap, fill cells) were blackboxed during STA — expected/normal for small test designs.
