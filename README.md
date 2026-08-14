# Variable-Geometry Drone Project

A custom-built FPV drone with mechanically extendable arms adjustable mid-flight, 
allowing real-time switching between high-stability and high-agility flight modes.

## Concept

This drone features a telescoping arm mechanism that allows each arm to extend or contract, changing the distance between the motors and the center of the frame. Extending the arms increases the moment of inertia, producing greater stability and improved hover efficiency through reduced propeller interference. Contracting the arms decreases rotational resistance, enabling faster and more agile flight. The goal of this project is to validate that a single drone platform can dynamically switch between these two flight profiles, and to quantify the measurable differences in flight characteristics between arm configurations through Betaflight Blackbox data collection.

## Current Status
- ✅ Frame research and arm extension mechanism design
- ✅ Parts selection and budget finalized
- ✅ CAD complete — stress simulations validated, STL files exported
- ✅ 3D printer received — fabrication in progress
- ✅ Electronics assembly
- ✅ Betaflight configuration and first hover test
- ✅ Prototype 1 flight confirmed — hover video recorded
- ⬜ Arm extension and contraction flight testing (Prototype 2)

## Built With

**CAD & Design**
- SolidWorks — 3D modeling, stress simulation, STL export

**Frame**
- Material: PETG, custom variable-geometry design
- Printed on: Elegoo Centauri Carbon 1

**Electronics**
- Motors: EMAX ECO II 2306 1700KV ×4
- FC + ESC Stack: SoloGood F405 55A 4-in-1
- Battery: OVONIC 6S 1300mAh 120C XT60
- Receiver: RM RP1 ELRS 2.4GHz (SpeedyBee)
- Transmitter: BETAFPV LiteRadio 2 SE ELRS V3
- Props: HQProp V2S 5x4.3x3 Tri-blade ×16
- Charger: SKYRC B6Neo

**Hardware**
- Arm locking: M3 threaded steel rods + thumb nuts
- Frame fasteners: M3 brass heat-set inserts
- Connectors: XT60 pigtail
- Soldering Kit: Q-Ming Soldering Kit
- Rosin Core Soldering Wire
- Liquid Solder Flux Dropper
- M3 Washers 100Pcs
- Aluminum Standoffs: Unlorpsy 10Pcs Red Femal Round Aluminum Standoffs 25mm 

## Documentation
- [Build Log](./Build-Log.md) — full design history, iteration notes, and fabrication updates
- [Docs/parts-list.md](./Docs/parts_list.md) — final parts list and budget
- [Images](./images) — CAD renders, simulation results, fabrication photos

## Goals
Complete first manual test flight with working arm extension mechanism by August 2026.
