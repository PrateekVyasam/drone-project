# Build Log

All design decisions, iterations, failures, and changes documented chronologically.

---

## Update 1 — Research and Parts Selection · May 28, 2026

**What I did:**
Defined project goals and selected all major components. Target all-up weight set at 950g 
with a 1000g hard ceiling. Estimated build weight at 642–742g leaving 258–358g margin 
for the arm extension mechanism.

**What worked:**
Component selection came together within budget. All major parts identified and priced.

**What failed or needed changing:**
Nothing at this stage — research phase only.

**What I changed:**
N/A — initial selection.

---

## Update 2 — Frame Design · May 29, 2026

**What I did:**
Designed elongated octagonal base plate (250x90mm, 0.5mm fillets, 25mm thick) in 
SolidWorks. Began planning the arm mechanism as a separate component from the frame.

**What worked:**
Base plate geometry established. Octagonal shape provides good mounting area for 
components while keeping weight manageable.

**What failed or needed changing:**
Still undecided on how to integrate the arm mechanism into the base plate — kept 
separate for now pending further design work.

**What I changed:**
N/A — design still in early iteration.

---

## Update 3 — Arm Mechanism Design · May 30, 2026

**What I did:**
Switched from individual arm mechanisms to integrating the outer arm channel directly 
into the base plate. Designed a telescoping arm system using two nested rectangular 
channels. Outer channel fixed at 40×25mm with 2mm walls, 150mm long. Inner channel 
at 35×20mm with 2mm walls, 200mm long, sliding within outer channel with 0.5mm 
clearance each side. Added a spring-loaded pin lock mechanism using a spring housing 
block inside the inner channel with a cylindrical pin engaging holes in the outer channel 
at contracted and extended positions. Also added 30.5×30.5mm FC/ESC standoff peg 
pattern and 4 standoff pegs for top plate integration.

**What worked:**
Telescoping channel concept proven viable in CAD. Pin lock positions at 20mm from each 
end of outer channel provide clean extended and contracted positions.

**What failed or needed changing:**
Spring-loaded pin mechanism flagged as potentially unreliable under vibration — will 
revisit locking approach in future update.

**What I changed:**
Motor end of inner arm thickened to 5mm walls to accept M3×6 self-tapping screws for 
motor mount attachment.

---

## Update 4 — Stress Simulation · May 31, 2026

**What I did:**
Ran SolidWorks static simulation on base plate and arm assembly using Nylon 6/10 as a 
conservative material approximation for PETG. Applied 750N load at motor end face — 
approximately 75x actual motor thrust — to stress-test the design well beyond real 
operating conditions.

**What worked:**
Maximum von Mises stress result of 5.28 MPa against a yield strength of 139 MPa. 
Stress is 3.8% of failure stress — arm geometry confirmed structurally sound with large 
safety margin.

**What failed or needed changing:**
Arm root junction identified as highest stress concentration point.

**What I changed:**
Flagged arm root junction for fillet addition in next design iteration to distribute stress 
concentration at that interface.

---

## Update 5 — Dimensions Update · June 1, 2026

**What I did:**
Rescaled all components to fit within standard 3D printer build volume constraints. Base 
plate reduced from 250x90mm to 130x80mm. Outer channel shortened from 150mm to 
80mm. Inner channel shortened from 200mm to 100mm and wall thickness increased from 
2mm to 5mm. Added 4 diagonal 2.5mm diameter holes for motor mount M3 screw 
attachment extruded 5mm deep for self-threading.

**What worked:**
All components now fit within printer build volume. Motor mount attachment points 
integrated cleanly into inner arm end.

**What failed or needed changing:**
Original dimensions were too large for practical printing without splitting parts. Inner arm 
mech further shortened from shortened version to 150mm after fit review.

**What I changed:**
All dimensions rescaled. Hole placements updated to match new geometry throughout.

---

## Update 6 — Base Plate Refinements and Parts · June 2, 2026

**What I did:**
Refined base plate geometry by removing excess material from the sides. Adjusted peg 
height and width to be smaller. Created the top base plate. Reviewed parts budget and 
found original receiver over budget.

**What worked:**
Material removal reduced overall frame weight without affecting structural performance. 
Top plate created with matching geometry to base plate.

**What failed or needed changing:**
Original receiver (MATEKSYS ExpressLRS 2.4GHz at $26) was over budget. Spring lock 
mechanism flagged again as unreliable — decided to replace with a different locking 
approach entirely.

**What I changed:**
Switched receiver to ELRS Receivers Series at $20. Spring lock mechanism removed — 
alternative locking solution to be designed in next iteration.

---

## Update 7 — Motor Mount, Top Plate Refinements, and Parts List · June 4, 2026

**What I did:**
Designed motor mount with 16×16mm mounting hole pattern to match EMAX ECO II 2306 
motor spec. Refined top plate with peg insert holes. Adjusted all peg heights after finding 
top plate clearance was too tight. Updated parts list with several component changes.

**What worked:**
Motor mount hole pattern confirmed correct for motor spec. Top plate peg hole alignment 
clean. Switched to heat-set brass threaded inserts for all mounting interfaces — 
significantly more reliable than self-tapping screws under vibration.

**What failed or needed changing:**
Original peg heights left insufficient clearance between base plate and top plate. 
Flight controller was over budget. Fillets at inner arm mounting interfaces were causing 
fit issues — parts not seating correctly.

**What I changed:**
Peg heights reduced to increase clearance. Flight controller replaced with lower-cost 
alternative saving approximately $30 while maintaining full compatibility. Fillets removed 
at mounting interfaces to achieve tighter, more precise mechanical fit. Added pigtail 
XT60 connector for cleaner battery connection. Transmitter selection still pending.

---

## Update 8 — Assembly Stress Simulation and CAD Finalization · June 7, 2026

**What I did:**
Ran final SolidWorks static stress simulations on all critical components under actual 
motor thrust loading (8.3N per motor, representing 850g thrust at full throttle on 6S). 
Finalized full assembly and exported all STL files for printing.

**What worked:**
Inner arm assembly: peak von Mises stress of 0.063 MPa against PETG yield strength of 
37 MPa — safety factor of approximately 587:1. Arm is structurally sound under full 
thrust loading.

Full drone assembly: peak stress of 6.031 MPa against same yield strength — safety 
factor of approximately 6:1. All critical load cases passed.

Standoff pegs passing through top plate holes confirmed as correct approach — provides 
lateral bracing at both ends and eliminates cantilevered vibration failure mode.

Locking mechanism simulation deferred — M3 threaded steel rods and nuts are orders 
of magnitude stronger than applied loads. No simulation required.

**What failed or needed changing:**
Minor stress concentration identified at motor mount junction. Does not require design 
changes at current load levels but will be monitored during flight testing.

**What I changed:**
Fillet radii maintained at peg bases to distribute stress at mounting interfaces. STL files 
exported and organized by part for printing. All simulation results saved to images 
folder — see images/update-8/.

---
