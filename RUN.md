# How to Run — Full Adder RTL to GDS Flow

## 1. Activate the OpenLane Python environment

cd OpenLane
source venv/bin/activate
export PDK_ROOT=<path-to-sky130-pdk>

## 2. Launch OpenLane (auto-starts the tool container)

openlane --pdk-root $PDK_ROOT path/to/full_adder_rtl2gds/config.json

## 3. Inside the container, run the flow

cd /openlane
./flow.tcl -design full_adder

## 4. Check output GDS

ls designs/full_adder/runs/<RUN_TAG>/results/final/gds/
