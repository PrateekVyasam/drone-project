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

## Update 9 — Motor Mount Redesign and Slicer Learning Curve · June 25 – July 9, 2026

**What I did:**
Received all electronics and invested in an Elegoo Centauri Carbon 1 3D printer for 
this and future projects. Spent approximately two weeks focused entirely on the motor 
mount — the smallest part of the drone — which turned out to be the most educational 
phase of the build so far. This period was largely a slicer learning curve, using the 
motor mount as the test piece since it uses the least filament of any component.

Filament choice confirmed as PETG throughout — chosen for its balance of durability, 
weight, and vibration resistance, which is critical for a drone that will crash during 
testing.

**What worked:**
By the end of this phase the motor mount design is structurally sound and passes a 
real load test — a school lanyard was attached to the motor mounting face and 15 lbs 
of weight was hung from it without failure. The final slicer settings with increased wall 
loops and infill density on the full part (without a modifier block) produced a clean, 
strong print with no visible seam vulnerabilities.

Heat-set brass inserts in the inner arm mechanism provide a reliable threaded interface 
for the motor mount screws. Tightening method confirmed: hand-tighten then turn 
approximately 5 small notches with a screwdriver until snug — no gaps between motor 
mount base and inner arm surface.

**What failed or needed changing:**

*Problem 1 — Motor wire clearance:*
The original motor mount hole pattern was centered on the base, but the EMAX ECO II 
2306 motors have a rigid section of wire that cannot bend. With the mount centered, 
this rigid wire had no clearance and could not fit. Making the mount longer risked 
structural integrity, so the hole pattern was moved to the front edge of the base 
instead. Full redesign done in SolidWorks.

*Problem 2 — Neck fragility on first prints:*
The neck section of the motor mount broke with minimal force on early prints. Added 
a modifier block in Orca Slicer targeting the neck area and increased wall loops to 10 
and infill density to 10% in that zone only — keeping the rest of the part lighter. The 
neck passed the 15 lb load test but a crack formed on the base plate instead, 
indicating the base was now the weak point.

*Problem 3 — Modifier block seam:*
Removing the modifier block revealed a visible layer seam at the boundary where the 
modifier block started — this seam was actually more vulnerable to breakage than the 
original neck. Modifier block removed entirely.

*Problem 4 — Base plate cracking under screw force:*
When screwing the motor mount to the inner arm, the base plate cracked — first with 
M3 screws alone, then again using a nut as a temporary spacer. Research identified 
the cause: PETG cannot withstand the compressive force of an overtightened screw 
regardless of print settings.

**What I changed:**
Increased base plate thickness by 2–3mm in SolidWorks to address the cracking under 
load. Removed the modifier block and instead increased wall loops and infill density 
uniformly across the entire part — this eliminated the seam vulnerability while keeping 
weight reasonable. Confirmed correct tightening method: hand-tight plus approximately 
5 small screwdriver notches until snug. This produced zero gaps between mount and 
arm with no cracking.

## Update 10 — Inner Arm Mechanism · July 9 – July 16, 2026

**What I did:**
Designed, iterated, and finalized the inner arm mechanism — the sliding arm that 
extends and contracts within the outer sleeve. This is the most structurally complex 
part of the build. Used small sample prints throughout to test settings and geometry 
before committing to full prints, running approximately 3–4 sample iterations before 
printing each final version. This saved significant filament compared to reprinting the 
full part each time.

The final geometry resembles an upside-down pair of aviator glasses when viewed from 
above — two separated hollow rectangular openings rather than one continuous hollow 
channel. The center section between the two openings is deliberately sized to 
accommodate a gear for the future automated arm mechanism. Chamfers were added 
throughout in SolidWorks — on the inner edges of the hollow openings and the majority 
of outer edges — primarily to improve sliding fit within the outer sleeve rather than for 
print quality.

**What worked:**
Vertical print orientation was the correct final choice. Printing vertically eliminated the 
need for supports entirely — the motor mount holes which caused significant support 
removal difficulty when printing horizontally printed cleanly in vertical orientation 
without any support material. This also reduced total filament usage compared to 
horizontal printing with supports.

The separated hollow geometry reduced bridging distance significantly compared to the 
original continuous hollow design, producing cleaner internal surfaces. Heat transfer 
from motors to the arm is not a concern — the part is solid enough that it would require 
significantly more heat than the motors produce to cause any warping.

Sample print approach proved highly effective — testing bridging and slicer settings on 
small sections of the part before printing the full version saved considerable filament 
and time across multiple iterations.

**What failed or needed changing:**

*Problem 1 — Print orientation and bridging:*
Initial prints attempted horizontally to reduce print time and filament. However the 
hollow interior required bridging across a long unsupported span, producing significant 
filament drooping and stringing inside the part. Multiple slicer adjustments were made 
to address this including reducing bridge speed, increasing fan speed for faster cooling 
and earlier solidification, and reducing internal bridge flow ratio from 0.95 to 0.80. 
These changes improved but did not fully resolve the drooping.

*Problem 2 — Warping on horizontal prints:*
Horizontal printing also introduced first layer warping on the corners. A brim was 
added to improve bed adhesion and reduce warping, which helped but added post-print 
cleanup time.

*Problem 3 — Weight:*
The redesigned geometry with separated hollow openings and additional material 
between them added weight compared to the original design. Each inner arm mechanism 
weighs approximately 70 grams as printed. With four arms required this contributes 
280 grams to the total all-up weight — a significant portion of the weight budget and 
an open problem going into the next phase.

**What I changed:**
Switched final print orientation to vertical — no supports required, cleaner motor mount 
holes, reduced filament usage compared to horizontal with supports. Redesigned hollow 
geometry from one continuous opening to two separated openings with chamfered edges, 
reducing bridging distance and improving sleeve sliding fit. Center section between 
openings intentionally retained for future gear integration in the automated arm phase. 
Arm weight flagged as an area for potential redesign in a future iteration if all-up 
weight proves problematic during flight testing.

**Open problem:**
At 70g per arm and 4 arms total, the inner arm mechanisms alone account for 280g 
of the all-up weight. This will be monitored during flight testing. If thrust-to-weight 
ratio proves insufficient, the arm geometry will be revisited to reduce material in 
non-structural areas.

## Update 11 — Outer Arm Sleeve · July 16 - 23, 2026

**What I did:**
Designed and iterated the outer arm sleeve — the fixed channel integrated into the 
full frame that the inner arm mechanism slides within. Used the same sample-print 
approach as the previous update, printing small sections of the outer sleeve and a 
full-length sample of the inner arm mech to test fit and sliding before committing to 
printing the full frame.

Progression: outer sleeve samples confirmed working → printed full-length inner arm 
mech → printed full-length outer sleeve → confirmed fit → printed full frame.

**What worked:**
Final locking mechanism is clean and reliable. The outer sleeve has a single slot on 
top. The inner arm has two holes on its top face that align with this slot at both the 
contracted and extended positions. A screw passes through the slot into the hole with 
a washer sitting on top of the outer sleeve — the washer allows controlled tightening 
to whatever tension is needed to lock the arm securely without overtightening. This 
replaced the original two-slot design and is both stronger and lighter since it requires 
fewer screws.

Sliding friction is intentionally calibrated — smooth enough to slide freely by hand 
but with enough resistance to prevent slipping under flight loads. Deliberately kept 
at this level rather than making it frictionless, since the automated version in 
Prototype 2 will require different friction characteristics anyway.

Bridging flow ratio finalized at 0.86 — this resolved the internal drooping issue 
that carried over from the inner arm mech phase. Now correctly identified as the 
primary bridging fix.

Also worth noting: the separated hollow opening geometry in the inner arm mech 
served a dual purpose beyond reducing bridge distance — it reduces the contact 
surface area between the inner arm and the outer sleeve wall, which directly 
contributes to smoother sliding. Less surface contact means less friction.

**What failed or needed changing:**

*Problem 1 — Fit too tight despite correct dimensions:*
The inner arm mech would not fit inside the outer sleeve even though CAD dimensions 
had the correct clearance. This is a known FDM printing characteristic — filament 
expansion causes printed parts to run slightly larger than modeled dimensions. 
Gradually increased the offset in 0.2mm increments and landed on 0.5mm clearance 
in CAD to achieve the intended real-world fit.

*Problem 2 — Rough sliding and cracking from two-slot design:*
With the initial 0.5mm offset, the inner arm slid through but was extremely rough — 
required hitting the screwdriver handle to extract it. The two slots on either side of 
the outer sleeve wall also cracked the sleeve edge when the inner arm was mid-travel 
on a sample print. Two slots removed material from both sides simultaneously, 
reducing wall rigidity significantly.

*Problem 3 — Slicer compensation values:*
Two Orca Slicer settings adjusted to improve dimensional accuracy:
XY hole compensation set to 0.1mm — improves accuracy of circular hole geometry.
XY contour compensation set to -0.15mm — slightly reduces outer perimeter size, 
bringing printed dimensions closer to CAD intent and improving sliding fit.
These two values in combination with the 0.5mm CAD offset produced the correct 
real-world sliding clearance.

**What I changed:**
Removed side slots entirely — replaced with single slot on top of outer sleeve only. 
This increased wall rigidity, eliminated the cracking failure mode, reduced screw 
count, and decreased overall drone weight slightly. Locking mechanism redesigned 
around top slot with washer and screw as described above. Slicer compensation 
values dialed in as above. Bridging flow ratio set to 0.86 across bridged sections.

## Update 12 — Drone Frame · July 23 - 25, 2026

**What I did:**
Printed the full drone frame using the same slicer settings established during the 
outer arm sleeve phase. Before printing, made several structural and printability 
design changes to the frame in SolidWorks based on lessons learned from earlier 
iterations.

**What worked:**
Slicer settings transferred cleanly from outer sleeve samples to the full frame print. 
Aluminum standoffs performed as intended — 25mm standoffs screw up from the 
underside of the drone through washer-clearance holes, protrude above the frame, 
and the top plate screws directly onto them, creating clean spacing between the top 
plate and internal components without relying on printed material for structural 
support.

Heat gun warping fix proved effective. A sample inner arm mech was inserted into 
the warped sleeve with a paper towel barrier to prevent fusing, then a heat gun was 
applied to the warped tips while pressing flat with a hard object. Warp reduced 
significantly — minor residual warp remains but does not affect arm sliding or locking 
mechanism function. No reprinting required.

Print orientation decision — printing the frame with the top face down on the bed 
meant the arm locking slots printed directly on the build plate rather than requiring 
bridging. This eliminated bridge defects at the slot locations entirely.

**What failed or needed changing:**

*Problem 1 — Printed peg vulnerability:*
Original design used printed PETG pegs to mount the top plate and to serve as 
standoffs for the ESC and flight controller. In a crash these pegs would be the first 
point of failure — breaking them would effectively total the frame. All printed pegs 
removed from the design.

*Problem 2 — Bridging over slot openings:*
Original print orientation would have required the printer to bridge over the arm 
locking slots, producing unreliable surface quality in a structurally critical area. 
Resolved by flipping the print orientation so slots face the build plate and print 
without any bridging.

*Problem 3 — Tip warping on outer arm sleeves:*
The tips of the outer arm sleeves within the frame warped during printing. Addressed 
post-print with heat gun as described above rather than reprinting — reprinting was 
not viable due to the significant filament cost of the full frame.

**What I changed:**
Removed all printed pegs. Replaced top plate mounting and component standoffs with 
the following system — washer-clearance holes on the underside of the frame accept 
screws from below, heat-set inserts on the top face of the frame receive those screws, 
25mm aluminum standoffs thread onto the protruding screw ends above the frame, 
and the top plate screws onto the standoffs. This creates a crash-resistant mounting 
system where the aluminum standoffs absorb impact rather than printed PETG. Frame 
print orientation flipped to eliminate bridging over slot locations.

## Update 13 — Print Completion, Assembly, and Electronics · August 2026

**What I did:**
Completed all printing for Prototype 1 after over 100 hours of total print time. 
The full frame prints as one complete part. Additional printed components: 4 inner 
arm mechanisms, 4 motor mounts, and 1 top plate — 10 printed parts total. Only 
print failure across the entire build was the outer sleeve tip warping documented 
in Update 12, resolved with the heat gun method.

Completed full mechanical assembly and electronics installation.

**Mechanical assembly changes from original design:**

Replaced nuts-as-spacers with proper washers for motor mount attachment — 
cleaner interface and slight weight reduction. Pressed all brass heat-set inserts 
into designated holes across the frame. Installed long M3 screws through the 
frame underside to serve as standoffs for the ESC and flight controller stack.

**Electronics assembly:**

Motor wire extension — the telescoping arm mechanism creates too much distance 
between the motors and ESC for the stock motor wires to reach. Purchased 23 feet 
of 20 AWG silicone wire matching the original motor wire gauge. Extended each 
motor wire by stripping both ends, twisting them together, soldering the joint, 
and finishing with heat shrink tubing. Repeated for all 12 motor wires across 4 
motors.

Soldering sequence: soldered all 4 motors with extended wires onto the ESC pads, 
soldered the XT60 battery connector onto the ESC after tinning the pads manually, 
slid the flight controller onto the ESC stack, then soldered the receiver wires 
directly onto the designated pads on the flight controller.

This was first-time electronics soldering. Common issues encountered on early 
joints included solder adhesion and spiking when withdrawing the iron. Approach 
used: complete all instances of one connection type, identify what went wrong on 
the first attempt, apply the correction to subsequent connections, then return to 
fix the first. By the end of each connection type the technique had improved 
significantly.

**Bench testing:**

After assembly, connected to Betaflight via USB. Navigated to the motor tab and 
spun each motor individually to verify correct function. All four motors confirmed 
operational. Propellers were not installed during this test. Receiver binding and 
basic flight controller configuration completed in Betaflight.

**Status:**
Prototype 1 is fully assembled and bench tested. Ready for first flight attempt.

## Update 14 — Final Assembly and First Flight · August 2026

**What I did:**
Completed final assembly and conducted the first flight of Prototype 1.

Assembled the top plate onto the aluminum standoffs and mounted the battery 
on top using three rubber bands — sufficient for a testing prototype where no 
aggressive maneuvers were planned.

Bound the transmitter to the receiver and configured two auxiliary switches 
in Betaflight: one switch to arm the drone, one to enable Angle Mode — a 
stabilization mode that prevents the drone from flipping during basic 
control inputs by leveling itself automatically.

**What worked:**
Transmitter binding and Angle Mode configuration both confirmed working. 
Battery mounting with rubber bands held securely through the flight with 
no slippage. Drone achieved stable flight.

Balance verification method: held the fully assembled drone at its center 
point by hand to check attitude. Initial battery placement at the center 
of the top plate caused noticeable forward bias. Moving the battery slightly 
aft of center produced a balanced attitude confirmed by hand before flight.

**What failed or needed changing:**

*Problem 1 — Transmitter binding process:*
No prior experience with binding an ELRS receiver. Had to learn the process 
from scratch — connecting the receiver through the Betaflight wifi interface 
and matching the transmitter passphrase.

*Problem 2 — Throttle range error in Betaflight:*
After binding, Betaflight flagged a throttle error caused by the throttle 
channel maximum value being outside the safe range. Resolved by manually 
entering the correct values through the Betaflight command line interface — 
throttle range set to 1000 minimum, 2000 maximum, with 1500 as the idle 
mid-point. This is standard ELRS throttle calibration.

*Problem 3 — Forward center of gravity:*
With the battery centered on the top plate the drone was noticeably front 
heavy in the first flight. Repositioned battery aft of center and reconfirmed 
balance by hand before the second flight.

**Status:**
Prototype 1 airborne. First flight confirmed basic functionality — motors, 
receiver, flight controller, and stabilization all working. Center of gravity 
issue identified and corrected. Second flight and arm extension testing 
documented in Update 15.

## Update 15 (Final For Prototype 1) — Second Flight, Frame Failure, and Proof of Flight · August 2026

**What I did:**
Conducted the second flight of Prototype 1 with the revised objective of 
testing arm extension and contraction differences in flight characteristics.

**What worked:**
First flight in the confined space confirmed stable, controllable flight 
in calm conditions. Prototype 1 demonstrated that the variable-geometry 
frame design is structurally and aerodynamically viable under controlled 
conditions.

After the crash, taped the cracked frame sections and conducted a third 
flight to confirm the drone could still achieve stable flight in its 
repaired state. Successfully hovered for 40 seconds — recorded on video. 
Proof of flight confirmed for Prototype 1.

**What failed:**

*Frame failure:*
Moved to an open field to allow more space for arm extension testing. 
Wind conditions were stronger than anticipated. The drone was blown into 
concrete, cracking the main frame and two of the four outer arm sleeve 
sections on impact. With the frame compromised, arm extension and 
contraction testing was not possible — the primary research objective 
for Prototype 1 could not be completed this flight.

*Motor heat under high throttle demand:*
All-up weight required motors to run at half throttle or above to 
maintain hover. After landing, motors were hot to the touch. Sustained 
operation at this throttle level risks heat transfer to the PETG motor 
mounts over time, potentially causing warping or structural softening 
at the mount interface. This is a known risk for Prototype 2 to address 
through weight reduction.

**Revised objective:**
Given the damage, the objective was revised — demonstrate that Prototype 1 
can achieve stable flight. This was confirmed across all three flights 
and documented in a 40-second hover video. The fundamental concept is 
validated — a variable-geometry quadrotor frame is buildable and flyable 
from scratch using FDM-printed PETG components.

**Findings and failure analysis:**
The crack location — outer arm sleeve sections — is consistent with the 
stress concentration identified in static simulation. Dynamic impact 
loading from a concrete collision far exceeds the static thrust loads 
modeled in simulation. The outer arm sleeve junction is confirmed as the 
primary structural vulnerability under real-world loading conditions.

PETG at current wall thickness and infill is adequate for flight 
vibration loads but insufficient for impact resistance. Motor heat at 
sustained high throttle is a secondary risk to PETG motor mounts that 
was not anticipated in the original design.

**Status:**
Prototype 1 objective met — stable flight confirmed and recorded. 
Arm extension testing deferred to Prototype 2. Build log for 
Prototype 1 complete.

## Prototype 1 — Known Issues Summary

The following problems were identified during the Prototype 1 build and 
flight testing. All will be addressed in Prototype 2.

**Weight and Thrust Efficiency:**
- All-up weight of approximately 1kg (2.2 lbs) required motors to sustain 
  above half throttle to maintain hover, causing motors to run hot to the 
  touch after flight — risk of heat warping PETG motor mounts over time
- The separated hollow opening geometry in the inner arm mechanisms, while 
  reducing sliding friction against the outer sleeve, added significant 
  weight compared to the original continuous hollow design — original 
  geometry should be reconsidered for Prototype 2
- Excess printed material directly beneath the propeller disk disrupts 
  thrust airflow and reduces overall flight efficiency
- Overall frame size may be a contributing factor to excessive weight — 
  a smaller footprint in Prototype 2 would reduce both print time and 
  all-up weight

**Structural:**
- No landing stands included in the design — hard landings transferred 
  impact force directly to the frame, increasing likelihood of cracking 
  during testing
- Aluminum standoffs came loose during hard landings, requiring 
  retightening between flights

**Wiring:**
- Extended motor wires routed externally are at risk of contact with 
  propellers — temporarily secured with double-sided tape as a field fix. 
  Wire routing must be integrated into the CAD design in Prototype 2 
  rather than managed post-assembly

**Motor Mounting:**
- Two of four motors did not sit fully flush against their motor mounts — 
  flat enough to fly but not to specification. Motor mount interface 
  geometry needs refinement in Prototype 2

**Research Objective:**
- Arm extension and contraction flight testing not completed due to frame 
  failure on second flight — primary research objective deferred to 
  Prototype 2
