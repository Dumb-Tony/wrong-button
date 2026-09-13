# Machine chapters

User direction, 13 September 2026: repeating the same machine for 24 jobs becomes boring. Replace that campaign with 3–5 progressively complex jobs per machine, then change machines. Current implementation uses four jobs each on two machines.

| Job | Machine | Challenge |
| --- | --- | --- |
| 1. First shift | Forklift | Discover power, wheel brake, travel and lifting; one broad bay. |
| 2. Listening door | Forklift | Add a powered sound receiver and horn-operated shutter. |
| 3. Inspection lane | Forklift | Stop and brake for an inspection stamp, then pass a low clearance. |
| 4. Forklift finale | Forklift | Two stamped deliveries through a door; park and shut down. |
| 5. A different attraction | Magnetic gantry | Discover close alignment, magnetic coupling and release into a broad bay. |
| 6. Up and over | Magnetic gantry | Hoist cargo above an 80-unit divider. |
| 7. Narrow landing | Magnetic gantry | Reverse direction over a taller 125-unit divider into a narrow bay. |
| 8. Crane finale | Magnetic gantry | Deliver two steel loads to opposite sides of a 105-unit divider. |

## Machine relationships

1 powers either machine. 3 controls its wheel/rail brake. Arrows set horizontal travel; Down centers the selector. Holding Space raises the carriage or hoist; releasing lowers it while powered. On the forklift, 2 sounds the horn. On the gantry, the visibly square teal control toggles a magnet that requires power. The new machine is announced at the handoff, and its scene, observations, accessible state and hints change accordingly.

The gantry head couples within 18 horizontal units and 4 vertical units of a steel load. Attached loads follow the trolley and cannot cross a divider below its top. The empty head also respects the divider. Turn off the magnet to detach; loss of power also releases a load. Dropped loads settle on the floor or divider and can be recovered. Matching bays accept only detached loads at floor height, stable for one second. Delivered loads stay complete.

Forklift jobs preserve the established simulation: gates listen when powered, inspection requires power and braking for 1.5 seconds, height sensors stop a raised carriage, and parking requires neutral, brake on and power off for one second.

## Progress and navigation

All eight jobs are available from the board, grouped by machine. Next proceeds through the chapter and then changes machines. Job 4 explicitly offers “Meet the gantry.” Replay stays on the completed job; the final result returns to the board. Notes are shared between machines.

Rules/save version: `machine-chapters-1`, stored under `wrong-button-chapters`. Notes and sound migrate from `wrong-button-nightshift`, falling back to `wrong-button`. Previous numeric job records are deliberately not remapped. The previous keys are preserved. Storage failure leaves the game playable in memory.

## Validation

The browser harness covers complete simulation routes at 30/60/120 presentation schedules, real DOM keyboard replays across all eight jobs, rejection and recovery cases, navigation, machine-specific control semantics, and both legacy migrations. These tests establish functional behavior, not enjoyment or fresh-player comprehension. See PLAYTEST_LOG.md for actual results.
