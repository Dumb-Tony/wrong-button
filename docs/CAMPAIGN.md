# Night Shift campaign — rules nightshift-1

## Scope authorization

On 2026-09-13 the user explicitly requested autonomous expansion with as many levels as practical, with feedback after returning. That supersedes the earlier M1-only scope restriction. This release provides 24 authored jobs on the same consistent machine. It does not claim that the original fresh-player comprehension gate passed; human testing remains pending. The classic M1 file is preserved separately.

## Progression

Four shifts of six jobs. Every job is accessible from the job board (J), so feedback need not be blocked behind completion. Results offer Next job and Replay job. After the last job, the board appears; completing all 24 earns the closing message. Continue resumes the last selected/next job from a fresh attempt, not an in-progress physical snapshot. Notes and personal bests persist separately from attempts.

| Job | Name | Main challenge |
| --- | --- | --- |
| 01 | First shift | Original delivery direction |
| 02 | Back to the floor | Unload left from the platform |
| 03 | Long haul | Full-lane carry |
| 04 | Across the workshop | Reverse toward a left-side bay |
| 05 | A little precision | 30-unit bay |
| 06 | Two orders | Two crates, matched bays |
| 07 | Low bridge | Height-sensor passage |
| 08 | Underpass return | Reverse through the passage |
| 09 | The listening door | Powered sound receiver |
| 10 | Knock from the other side | Open the door from a reverse start |
| 11 | Mind the roof | Lower clearance, door, precise bay |
| 12 | Twin passage | Two loads through both obstacles |
| 13 | Weigh in | Stamp cargo at the inspection pad |
| 14 | Return receipt | Inspect a return delivery |
| 15 | Measured twice | Stamp two loads individually |
| 16 | Inspection lane | Inspection plus clearance |
| 17 | Signed and sealed | Inspection plus listening door |
| 18 | Checked at the door | Reverse route through all three systems |
| 19 | Clock out | Delivery, then powered-down parking |
| 20 | Crossed orders | Crates cross directions; park in the middle |
| 21 | Three tickets | Three individually matched deliveries |
| 22 | The night inspector | Two stamps, listening door, return parking |
| 23 | Tight schedule | Narrow return bays, sensor, stamp, door, parking |
| 24 | Last light out | Three loads, crossed routes, every system, parking |

## Authored rules (developer spoilers)

Inputs retain the M1 mapping. Power enables travel/hydraulics. The brake stops travel. Space raises while held, lowers on release while powered. Fork range 0–120; travel 100 units/s, raising 65/s, lowering 40/s. Pickup chooses the nearest undelivered crate within 74 units when a rising carriage crosses its underside. Only one crate is carried at a time. Crates are identified by letters as well as colors. Correctly settled cargo is accepted after one second and remains delivered for the attempt.

Listening doors stay closed until the horn is sounded while power is on; then they latch open until reset. The horn always remains a horn. The new relationship is the powered receiver attached to the door. Closed doors stop the vehicle without damaging it.

Clearance passages are height-sensor interlocks, not physical roofs. Their sign and current-height readout identify the allowed carriage height. Travel is denied while too high in the sensor zone; lowering recovers immediately. These are authored fictional constraints, not realistic forklift certification equipment.

Inspection pads stamp each crate after 1.5 seconds in range, with engine on and brake set. Cargo may rest on forks or floor. Required inspection must happen before delivery is accepted. A stamped crate keeps its receipt for that attempt. The bay rejects the wrong letter, an unstamped load or a hovering load.

Parking jobs require all deliveries, vehicle within 24 units of P, centered lever, brake set and power off for one second. No attempt timer failures. Reset only restarts the current job and retains notes/records. State uses fixed 1/120 steps with eight-step catch-up cap. Small epsilon tolerance handles floating-point accumulation at exact dwell thresholds.

## Validation boundaries

All authored routes have automated completion evidence. The route driver uses observed simulation state to issue controls and thus knows the solution; its times measure reproducibility, not novice performance or subjective enjoyment. Full human keyboard/touch feel, accessibility with a screen reader, difficulty ordering and fresh-player comprehension remain feedback gates. No fake testers or claimed playtime estimates.
