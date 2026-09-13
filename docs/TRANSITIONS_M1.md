# M1 transition table — rules m1-2

Developer reference: spoilers below. The game never labels these functions.

| Spatial input | Transition | Dependency | Visible / audible evidence |
| --- | --- | --- | --- |
| Upper left round | Toggle power | None | Engine vibration, striped lamp, low tone |
| Upper right round | Horn pulse | None | HONK caption and canvas pulse, high tone |
| Lower left switch | Toggle brake | None | Shoe visibly touches / leaves wheel, click |
| Right lever | Drive -1 / 0 / +1 | Power on AND brake released | Motion, or relay / strain caption |
| Bottom ribbed control | Hold raises; release lowers | Power on | Vertical carriage, motor / dry-click caption |

Simulation is a pure state transition at 120 Hz, maximum eight catch-up steps. Vehicle x is bounded 70–840; speed is 100 units/s. Fork travel is 0–120, raising 65/s, lowering 40/s. The floor is level to x560, ramps to elevation 48 at x720, then stays level. This is an authored puzzle, not training equipment.

Pickup needs the powered rising carriage within 76 units of the crate and crossing its underside. Carried cargo follows the vehicle; lowering onto terrain hands support back to ground/platform. A broad two-sided carriage deliberately permits pickup from either direction without an extra input. The bay requires crate center x754–800, platform support, y48, stable for one second. Hovering through the bay never wins. Completion is state-based, not an input sequence.

Tuning decisions: instantaneous brake, bounded movement, no unstable tipping physics, and release-to-lower reduce recovery friction. The ramp is shallow and cargo never disappears. M1 uses safe set-downs rather than a separate random drop mechanic; the reserved drops field remains zero. A deeper slapstick drop system is excluded from this core-verb experiment. The first hint only points to observable components. First attempts show no running time; successful attempts show time/actions/hints and unlock the visible replay timer. No medals or extra content.

Pause clears the held control and accumulator. Reset restores only attempt state; versioned notebook, sound setting and compatible best record survive. Storage exceptions fall back to memory. R asks before reset; Escape pauses; dialog Escape resumes a paused attempt. Result retry is one click. Explicit saved-data erase is confirmed.

Known simplifications: a fictional symmetric carriage, immediate wheel stop, no collision damage or inertia, no fork tipping, only one observational hint, no remapping, no second machine. Human comprehension and interest gates remain open.
