# Variable-Geometry FPV Drone

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

### Update 1 — Research & Parts Selection

Defined project goals: variable geometry FPV drone with mechanically extendable arms to study the effect of arm length on flight characteristics. Set target AUW of 950g with 1000g hard ceiling. Selected all major components: BrotherHobby Returner R5 2306 1750KV motors, Holybro Tekko32 F4 45A 4-in-1 ESC, Matek H743-Wing flight controller, Tattu 4S 1500mAh 75C battery, BetaFPV ELRS Nano receiver, HQProp 6x3x3 props. Estimated build weight at 642–742g leaving 258–358g margin for arm extension mechanism.

### Update 2 — Frame Design

Designed elongated octagonal base plate (130×80mm, 20mm chamfers, 4–5mm thick PETG) in SolidWorks. Arms extend from four chamfered corners at 45° in X configuration. Switched from sandwich frame concept to integrated design where arms are direct extensions of the base plate. Added 30.5×30.5mm FC/ESC standoff peg pattern (M3, 7mm height) at center of base plate.

### Update 3 — Arm Mechanism Design

Designed telescoping arm mechanism using two nested rectangular channels. Outer channel (fixed, 40×25mm, 2mm walls) is integrated into base plate. Inner channel (35×20mm, 5mm walls at motor end) slides within outer with 0.5mm clearance each side. Spring-loaded pin lock mechanism uses a spring housing block mounted inside the inner channel, with a cylindrical pin protruding through the top face to engage holes in the outer channel at contracted and extended positions. Pin holes in outer channel at 20mm from each end. Motor end of inner arm has thickened 5mm walls to accept M3×6 self-tapping screws for motor mount attachment.

### Update 4 — Stress Simulation

Ran SolidWorks Static simulation on base plate and arm assembly using Nylon 6/10 as conservative material approximation for PETG. Applied 750N load at motor end face (approximately 75× actual motor thrust). Maximum von Mises stress result: 5.28 MPa against yield strength of 139 MPa — 3.8% of failure stress. Arm geometry confirmed structurally sound with large safety margin. Identified arm root junction as highest stress concentration point, flagged for fillet addition.

### Update 5 — Motor Mount Design

Designed motor mount end cap for inner arm. Outer dimensions match inner arm face (35×21.5mm). Four M3 self-tapping screw holes (2.5mm diameter, 5mm depth) positioned on 22×10mm pattern within solid wall material. Hole pattern for BrotherHobby R5 2306 motor: 19×16mm between centers. Motor body diameter 27.7mm will overhang arm width which is standard for this motor size. All external edges filleted to 0.5mm for consistency across all parts.
