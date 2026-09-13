# Wrong Button — Game Design Document

## Elevator pitch
Operate an unfamiliar machine with unlabeled controls and a clear job. Experiment, observe, recover from funny mistakes and learn a consistent internal logic. The same machine that takes ten minutes to understand should eventually take seconds to operate.

## Design pillars
- Unknown controls, consistent causality.
- Knowledge is the main progression system.
- Mistakes create recoverable situations more often than failure screens.
- Machines reveal evidence; they do not demand blind guessing.

## Player fantasy
Become the person who understands an intimidating panel. The reward is a practiced sequence of actions that once seemed incomprehensible, not a purchased upgrade or a revealed answer sheet.

## Core gameplay loop
Read task → inspect machine and visible state → form a hypothesis → manipulate a control → observe consequences → revise understanding → recover or execute solution → finish → replay faster or move to a related machine. First attempts may last 5–12 minutes; mastered attempts may take under one minute. Those are targets, not forced timers.

## Controls
Pointer clicks buttons/switches and drags a lever. Keyboard Tab/arrows focus controls, Enter/Space activates, and directional keys adjust focused levers. Controls have neutral spatial names such as “upper round button” for accessibility, not hidden functional labels. R offers a clearly confirmed machine reset during an active run; Escape pauses. A separate single-click retry appears after completion. Optional player-written annotations are permitted after observation; the game must not auto-label all functions.

## Moment-to-moment mechanics
Press a button: hear a horn, see a status lamp, or watch the forks move. Try a lever while power is off and hear a relay click without motion. Start the engine, try again, and infer the dependency. A wrong action may drop cargo or reverse motion, but the player can retrieve the load. No untelegraphed irreversible action should erase ten minutes of experimentation.

## Physics and machine systems
Use explicit state variables and transition rules: power, brake, drive direction, fork height, load contact and goal occupancy. Controls change these variables; sensors and outputs expose their consequences. Stable mappings persist across retries and sessions. Shared visual shapes/symbols may emerge on later machines and always preserve their established meaning. A first machine can be fully unlabeled; later repeated symbols are vocabulary learned through play, not arbitrary decoration.

Separate input mapping, machine state, actuator motion, consequence simulation and objective validation. M1 physical motion is simple lane movement plus vertical forks, not a forklift simulator. A control that cannot act should still create an observable response, such as motor strain or a changing indicator. Use authored recoverable failure states; avoid random malfunction as puzzle difficulty.

## Scoring
Completion is the primary first-play reward; do not penalize experimentation before understanding. After completion, offer a mastery run scored primarily by elapsed time, then optional efficiency medals for fewer actions and recoveries. A “wrong press” cannot be universally defined because experimenting or honking may be intentional. Record actual action count, resets and cargo drops rather than judging guessed intent. Reset starts a new timed attempt but preserves annotations and completed-machine knowledge.

## Level and environment design
Present a compact control panel beside a clear machine view. The task names the desired result: place a crate in the loading bay. First machine has five inputs with observable independent effects and two simple dependencies. Later machines reuse power, hydraulics and direction concepts in new combinations. Conditional release: four machines—forklift, conveyor crane, excavator and compact submarine ballast station. These are fictionalized puzzle machines; real-world operational accuracy is not a goal. Spacecraft and enormous control rooms are backlog.

## Progression and unlocks
Completion unlocks the next machine; mastery medals are optional. Player knowledge carries forward through consistent rules, a local notebook and optional snapshots of discovered states. Hints use a staged ladder: point to a relevant observation, explain a relationship, then reveal an explicit step only on request. Hints never alter controls secretly. No XP or stat upgrades make a machine easier.

## Replayability
First discovery and subsequent fluency are different pleasures. Provide alternate objectives on the same understood machine, such as precise load placement or recovering a stalled line. Fixed controls enable speedruns. Randomized buttons would erase accumulated learning and are excluded from the main game; an optional remix would require separate labeling and records. Do not promise endless discovery from a finite machine set.

## Art direction
Tactile retro panels with consistent button shapes, lever detents and warm industrial colors. Machine view favors clear linkage between control and effect. Avoid meaningless decorative gauges that imply puzzle relevance. Complexity grows through understandable relationships, not tiny illegible labels.

## Animation and VFX
Button travel, lever resistance, relay lamps and visibly moving actuators communicate cause. Cargo drops are brief slapstick and leave recoverable objects. Trace a signal only through optional hint mode; normal play must preserve inference. Effects cannot obscure the state needed to solve the machine.

## Audio
Each actuator has a distinct sound family; power-on, stalled motor, horn and release are distinguishable. Pair every critical sound with a visible indicator or caption. Output sounds can reveal that a control was accepted even when a dependency blocks motion. Avoid verbal instructions that spoil the discovery.

## UI/UX
Keep the task visible, controls large and machine state in view. No tutorial names unknown functions. A neutral interaction tutorial may explain how to click, hold or drag. Notebook records player text and optionally neutral event observations; it does not infer answers. Goal validation explains which physical condition remains unmet in optional hints. Save completed machines and notes locally; allow resetting a machine without wiping knowledge.

## Accessibility and options
Full keyboard panel navigation, large hit targets, text scaling, captions, high-contrast indicators and no color-only dependencies. Provide DOM controls over or alongside Canvas so focus and accessible spatial descriptions are available. Optional extended motor travel time and untimed discovery reduce dexterity pressure. Screen-reader state descriptions should expose the same observable consequences as the visual scene, without disclosing hidden function names.

## Technical approach
M1 is DOM panel plus Canvas machine view. Encode state transitions as pure functions and visible actuators as bounded animations. Objective checks use simulated state, not button sequences, allowing alternate valid solutions. Add meaningful transition/invariant checks for power, brake and load placement. Store mappings as authored constants and notes/records through a versioned adapter. No generative puzzle system or complex physics engine is needed.

## Risks and mitigations
Unclear feedback becomes guessing: every input produces an interpretable observation. Too many dependencies overwhelm: begin with independent effects before combinations. Automatic annotations spoil discovery: use player-authored notes and optional hints. Reset destroys motivation: preserve knowledge and offer recoverable cargo. Familiar machinery may invite misleading assumptions: use stylization and consistent fictional rules rather than pretending to be a realistic training device.

## Scope boundaries
M1 is one machine, five inputs and one objective. Conditional release caps at four machines, two mastery tasks each, local notebook and optional hints. No cockpit simulator, procedural mystery generator, narrative campaign, online leaderboard, multiplayer or thousands of decorative controls.

## Milestone roadmap
1. **Standalone HTML vertical prototype:** one unlabeled forklift machine; prove experiment–observe–infer–operate without a manual.
2. **Knowledge transfer validation:** one second machine reuses two learned relationships. Fresh testers must benefit from what they learned without controls being identical.
3. **Small game:** four machines, alternate tasks, notebook and hint ladder; verify every objective is solvable from visible evidence.
4. **Polish:** keyboard/screen-reader parity, feedback, recoverability and records; test both novices and returning experts.
5. **Expansion review:** new machinery only when it adds relationships, not panel size. Multiplayer remains an independent later possibility.

## Development policy and evidence

This design originated as version 0.1, dated 2026-09-12; M1 implementation was authorized on 2026-09-13. It is not a production commitment. The source is the concept-development response in “Generate Game Ideas” (conversation 6aa59721-d164-83ea-966e-8f286439cfce), read in full for the seven selected concepts. The user's current brief takes precedence over older multiplayer brainstorming. Mechanical formulas, key bindings, content budgets, and test thresholds below are proposed hypotheses, not previously approved requirements or measured results.

Single-player first. No accounts, servers, matchmaking, replication, rollback, network authority, or multiplayer-driven entity architecture. A later multiplayer proposal requires its own feasibility and scope decision. Ordinary modular separation of input, simulation, presentation, and save data is sufficient now.

Milestone 1 is a standalone HTML vertical prototype whose sole purpose is proving the core mechanic/verb before expanding content. “Vertical” means a complete tiny start–play–result–restart loop, not production polish. M1 is implemented in prototypes/m1/index.html; human exit gates remain open. No full production build is included.

## Shared implementation and validation contract

Deliver the future M1 as one index.html with embedded CSS, JavaScript, geometry, and generated sound. It must open from file:// offline with no installation, build command, CDN, remote fonts, fetch, or external asset requirement. Use Canvas 2D for initial rendering, including projected geometry where specified. No engine decision for the full game is implied.

Use requestAnimationFrame for presentation and a fixed 1/120-second simulation accumulator, capped at eight catch-up steps. Discard excessive backlog after suspending a tab; pause on lost focus and clear held input. Tune to a stable 60 rendered frames/second on the actual test PC, whose CPU, GPU, browser, and resolution must be recorded. Compare repeated scripted input at 30, 60, and 120 rendered FPS; traversal/score differences above 2% need investigation. This is local repeatability, not a promise of cross-browser bitwise determinism.

Persist only settings and appropriate local records through a versioned localStorage adapter wrapped in try/catch. The game must remain playable in memory when storage is unavailable, especially under file://. Provide an explicit local reset action. Later ghost recordings must carry course, rules, and physics version identifiers. Never silently compare incompatible records.

Developer-only overlays report frame cost, simulation time, relevant physical variables, and reset state. M1 tests cover the normal loop, boundary cases, focus loss, rapid restart, and prolonged use. Do not invest in a general framework before a mechanic passes.

## Milestone governance

Milestones are exit gates, not promised calendar dates. At each gate, record observations, parameter changes, unresolved issues, and a proceed / iterate / park decision in docs/PLAYTEST_LOG.md. Recruit five fresh players where possible; an internal solo test can identify problems but cannot count as the fresh-player comprehension gate. Small samples are directional evidence.

M1 includes only the bespoke prototype specification in docs/PROTOTYPE_M1.md. Do not begin M2 merely because M1 runs without crashing. If the mechanic misses its enjoyment or readability gate, run up to two focused tuning rounds before deciding whether to revise the premise or park it. Adding levels, upgrades, story, or polished assets is not the remedy for an unproven verb.

