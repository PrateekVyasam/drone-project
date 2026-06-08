# Variable-Geometry Drone Project

A custom-built drone with mechanically extendable arms that can be adjusted mid-flight, allowing the pilot to switch between high-stability and high-speed flight modes on demand.

## Concept

Most drones are locked into a fixed frame geometry — optimized for either control or speed, but not both. This project explores a variable-geometry design where the arm length can be extended or contracted during flight, giving the pilot real-time control over the drone's flight characteristics:

- **Extended arms** — wider base increases moment of inertia, providing greater stability and control at lower speeds
- **Contracted arms** — smaller base reduces moment of inertia, enabling faster, more agile flight with reduced drag

The goal is a single drone that adapts to the situation rather than requiring separate builds for different flight styles.

## Current Status

- ✅ Frame geometry research and arm extension mechanism concept
- ✅ Parts selection and budget documentation
- 🔄 Frame design and prototyping in progress
- ⬜ Electronics integration and flight controller configuration
- ⬜ First test flight

## Built With

- **CAD modeling** — SolidWorks
- **Frame** — custom designed for variable arm geometry, PETG
- **Motors** — BrotherHobby Returner R5 2306 1750KV ×4
- **ESC** — Holybro Tekko32 F4 45A 4-in-1
- **Flight controller** — Matek H743-Wing
- **Battery** — Tattu 4S 1500mAh 75C
- **Receiver** — BetaFPV ELRS Nano
- **Props** — HQProp 6x3x3

## Goals

Complete first test flight with working arm extension mechanism by August 2026.

---

## Updates

### Update 1 (05/28/2026) — Research & Parts Selection

Defined project goals: variable geometry FPV drone with mechanically extendable arms to study the effect of arm length on flight characteristics. Set target AUW of 950g with 1000g hard ceiling. Selected all major components: BrotherHobby Returner R5 2306 1750KV motors, Holybro Tekko32 F4 45A 4-in-1 ESC, Matek H743-Wing flight controller, Tattu 4S 1500mAh 75C battery, BetaFPV ELRS Nano receiver, HQProp 6x3x3 props. Estimated build weight at 642–742g leaving 258–358g margin for arm extension mechanism.

### Update 2 (05/29/2026)— Frame Design

Designed elongated octagonal base plate (250x90mm, 0.5mm fillets, 25mm thick) in SolidWorks. Planning on creating the arm mechanism seperate from the frame, still deciding on how to integrate it to the frame itself. 

### Update 3 (05/30/2026) — Arm Mechanism Design

Switched from individual arm mechanisms to integrating the outer arm mechanism into the base plate itself. Designed telescoping arm mechanism using two nested rectangular channels. Outer channel (fixed, 40×25mm, 2mm walls 150mm long) is integrated into base plate. Inner channel (35×20mm, 2mm walls at motor end, 200mm long) slides within outer with 0.5mm clearance each side. Spring-loaded pin lock mechanism uses a spring housing block mounted inside the inner channel, with a cylindrical pin protruding through the top face to engage holes in the outer channel at contracted and extended positions. Pin holes in outer channel at 20mm from each end. Motor end of inner arm has thickened 5mm walls to accept M3×6 self-tapping screws for motor mount attachment. 

Additional Info: Added 30.5×30.5mm FC/ESC standoff peg pattern (M3, 7mm height) at center of base plate and 4 10mm stand off pegs in order to integrate a top plate.

### Update 4 (05/31/2026) — Stress Simulation

Ran SolidWorks Static simulation on base plate and arm assembly using Nylon 6/10 as conservative material approximation for PETG. Applied 750N load at motor end face (approximately 75× actual motor thrust). Maximum von Mises stress result: 5.28 MPa against yield strength of 139 MPa — 3.8% of failure stress. Arm geometry confirmed structurally sound with large safety margin. Identified arm root junction as highest stress concentration point, flagged for fillet addition.

## Update 5 (06/01/2026) - Dimensions Update

Changed the base plate dimensions to fit 3D printing standard: Base plate dimension is now 130x80mm (not including the outer rectangular channels). Outer rectangular channel is now changed from 150mm to 80mm, hole placement is the same. Inner rectangular channel changed from 200mm to 100mm, hole placement is the same, updated the 2mm thick wall to 5mm thick wall, added 4 2.50 diameter circles diagonally forthe purpose of attached a motor mount design with M3x6 screws, extruded down to 5.00mm, enough to self-thread. Additionally, Inner arm mech shortened from 200mm to 150mm, as well as hole placements.

### Update 6 (06/02/2026) — Base Plates and Parts

Edited the base plate by the following:
- Removed excess area by cutting off part of the sides
- Changed peg height and width to be smaller
- Created Top Base Plate

Parts for the drone had seemed to be out of budget, therefore I changed the original reciever (MATEKSYS ExpressLRS 2.4GHz Receiver ($26)) to ELRS Receivers Ser ($20), may change more components in future updates to cheaper alternatives if applicable. Additionally, changing spring lock to a different alternative.

## Update 7 (06/04/2026) — Motor Mount, Top Plate, Base Plate Refinements, Inner Arm Extension Model, and Parts List

Parts List Updates
- Switched to heat-set threaded inserts to improve structural rigidity and reduce vibration-related failures.
- Added a pigtail connector for simplified and more reliable battery connection.
- Replaced the flight controller with a lower-cost alternative (approximately $30 cheaper) while maintaining compatibility with existing components.
- Next step: selecting a compatible radio transmitter system.

## Design Progress

Motor Mount
- Designed a new motor mount featuring a 16×16 mm mounting hole pattern.
- Clearance for motor and propeller is still under review and may require adjustments in future iterations.

Top Plate
- Created the Top Plate with the same dimensions as the octogonal base (without the arms), and integrated the peg inserts. There are 4 holes on the top of the plate to screw into the pegs

Base Plate Refinements
- Adjusted all Peg heights, seemed like the top plate was too close and left little to no clearance

Inner Arm Extension
- Removed fillets at mounting interfaces to ensure a tighter and more precise mechanical fit.

## Update 8 (06/07/2026) — Assembly Stress Simulation, CAD Finalization, and Pre-Print Validation

## Stress Simulation Results:

- Ran SolidWorks static stress simulations on critical components to validate structural integrity before printing. Results are found in the Simulation Folder.

## Inner arm assembly: peak von Mises stress of 0.063 MPa against a PETG yield strength of 37 MPa, producing a safety factor of approximately 587:1. The arm is structurally sound under full motor thrust loading.

- Full drone assembly: peak stress of 6.031 MPa against the same yield strength, producing a safety factor of approximately 6:1. A minor stress concentration was identified at the motor mount junction and will be monitored but does not require design changes at current load levels.
- Locking mechanism: simulation deferred — arm locking will use M3 metal threaded rods and nuts, which are orders of magnitude stronger than the loads applied. No simulation required.

## CAD Finalization

- Assembly confirmed structurally valid across all critical load cases.
- Standoff pegs pass through corresponding holes in the top plate, providing lateral bracing at both ends and eliminating the cantilevered vibration failure mode.
- Fillet radii maintained at peg bases to distribute stress concentration at mounting interfaces.
- STL files exported and organized for printing.

## Status
CAD phase complete. 3D printer arriving June 21st. Electronics to be ordered during Amazon Prime Day (July 8-9). First print and assembly begins June 21st.

## Next Steps

- Print test arm first to verify slot dimensions and motor mount hole alignment before committing to full frame print
- Confirm motor rotation direction convention before finalizing arm orientation
- Order electronics — motors, ESC, flight controller, battery, receiver, props
