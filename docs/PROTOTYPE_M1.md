# Milestone 1 — Standalone HTML vertical prototype

**Status: M1 implemented on 2026-09-13; human validation pending.** The sole purpose of this milestone is proving the core mechanic/verb before expanding content. Follow the offline, fixed-step, restart, storage, and measurement contract in GDD.md. All thresholds are initial acceptance targets to validate, not completed test results.

## Question and hypothesis
Can players infer a consistent machine through visible consequences, then operate it substantially faster from memory?

## Exact playable slice
One side-view forklift lane, one crate and a loading platform. Task: place the crate in the marked bay. Five unlabeled inputs: latching power button, horn button, brake switch, forward/neutral/reverse lever, and hold-to-raise fork control that lowers when released. Forks have a safe lower stop. Machine movement requires power on and brake off; hydraulics require power. A shallow ramp and forgiving collision allow cargo recovery. Stable control positions and functions never shuffle.

## Implementation specification
Use variables power:boolean, brake:boolean, drive:-1/0/1, forkHeight, vehicleX, loadPose and loadSupported. Show engine vibration, brake mechanism and fork motion; denied movement produces a visible strain cue. Completion requires crate inside the bay, supported by the platform and stable for one second, independent of input sequence. No hidden timer failure. Include event-log debug mode and player-entered notes saved separately from attempt state.

## Deliberate exclusions
No functional labels, automatic solution journal, random remapping, second machine, realistic hydraulic simulation or cinematic failure. Hints are optional and their use is logged.

## Test procedure and exit gate
Five fresh players receive only the objective and generic click/hold/drag instructions. Four should solve within ten minutes with at most the first observational hint. After a brief unrelated break, three should complete a second run in less than half their first successful time and explain the power/brake dependencies. Track mistaken hypotheses and whether feedback corrected them. At least three should express interest in learning another machine.

Verify stable mappings across 20 resets, all inputs under power off, braking while moving, cargo recovery from either side and goal rejection when the crate merely passes through the bay. Check keyboard-only completion and that notes survive attempt resets.

## Decision rule and deliverables
One offline HTML, transition table and novice/replay timing notes. If players resort to random cycling, improve feedback or remove one dependency. If repeat play does not become faster, examine input friction and task layout. A puzzle solved only with a verbal walkthrough does not pass.

