# Wrong Button — Playtest log

## 2026-09-13 — M1, rules m1-2

Decision: **iterate / recruit fresh testers**. The bounded prototype is implemented. M1 comprehension, replay learning and interest gates are NOT passed. No M2 work began.

Hardware: AMD Ryzen 9 9950X 16-Core Processor; Windows reports AMD Radeon RX 9070 XT and AMD Radeon integrated graphics. Browser: Codex in-app Chromium; exact browser version and physical display resolution unavailable through this session. Captured viewport: 1265 × 712. GPU actually used by the browser was not measured.

Automated evidence (prototypes/m1/checks.html): start/play/result/restart; all actuator dependencies under power off; powered brake denial; braking while moving; 20 resets with fixed mappings and preserved notes; full pickup / ramp traversal / platform set-down / one-second settling route; focus-loss pause and held-input clear; no paused-time catch-up; recovery pickup from left and right; hovering crate rejected; one-hour simulated boundary soak; self-contained source check. Scripted route time was 11.500 seconds at each of 30, 60 and 120 render schedules (0% difference). These are virtual-clock tests, not measured novice/replay times. Synthetic keyboard events cover hold/release; ordinary button clicks model native activation. This does not establish a complete human keyboard-only route.

Browser interaction: actual Enter started the game and toggled the first button; Tab navigation reached the switch; Space released it, verified in the accessibility tree. Desktop screenshot inspected: readable scene, large control targets, visible ramp and marked bay. Developer readout sampled about 175.8 rendered FPS with frame cost rounded to 0.00 ms; that is one sample on this high-refresh host, not a sustained performance benchmark or a guarantee for other hardware. The fixed-clock regression provides independent simulation-repeatability evidence.

Tuning: broad symmetric carriage with 76-unit pickup reach, 100-unit/s travel, 65-unit/s lift, 40-unit/s lowering and immediate braking. These prioritize observation and forgiving recovery. No destructive drop states or random failures. One observational hint only. See TRANSITIONS_M1.md for full transition table and rationale.

Limitations: no fresh human testers, no subjective feel testing, no measured ten-minute novice gate, no after-break replay comprehension test, no interest-in-another-machine gate. Direct file:// navigation was blocked by the browser tool; the code is dependency-free but direct offline opening must still be checked in a normal browser. Node executable exited with no diagnostics, so tests run in the browser instead. Full human keyboard-only completion, mobile touch feel, screen-reader experience, sustained 60 FPS measurement and additional browser coverage remain open.

Next bounded experiment: give five fresh players only the objective and generic input instructions. Record mistaken hypotheses, first solve time, hint count, break/replay time, dependency explanations and voluntary interest. Require four solves within ten minutes with at most the observational hint; three replays under half the first time with correct explanations; three interested in another machine. If weak, tune feedback or friction before any new content.

Storage regression: explicitly throwing localStorage access still permits play and preserves in-memory notes across reset (PASS).

Recovery tuning round: the x810 right stop could strand right-side pickups short of the bay. Extended to x840; both left- and right-side pickup-to-delivery routes now pass, with normal 11.500-second FPS routes unchanged. Rules incremented to m1-2 before final release; complete recovery routes added to the harness.

## 2026-09-13 — Direct keyboard controls

User feedback: pointer-only operation felt awkward. Added global 1/2/3 shortcuts for the two round buttons and switch, Left/Down/Right for the three lever positions, and hold/release Space for the bottom control. No Tab focus is required. Visible keycaps and accessible shortcuts identify inputs without giving functional answers. Mouse controls remain available. Physics and existing notes/records remain compatible with m1-2.

Validation: full synthetic keyboard gameplay route passed at 11.500 seconds with no control clicks/focus changes. Existing recovery, timing, pause, reset and storage regressions passed. Added passing checks for toggle repeat suppression, Space on a focused toggle, Space release, notebook typing isolation and direct keys on the focused lever. Native browser key presses verified Enter start, 1, 3, Right, Down and Space with focus left on the first button; rendered keycaps inspected. These are automated browser interactions, not human feel testing. Fresh-player gates remain open.

## 2026-09-13 — Workshop aesthetics and UI pass

User requested visual/UI improvement before moving forward. Added a warm cream job card, amber/olive control panel with dimensional buttons, separate workshop status and observation areas, compact keyboard-aware toolbar, paper-style field notes, and redesigned start/pause/result dialogs. Completion now presents elapsed time, actions and hints in separate tiles. The workshop Canvas adds overhead lights, structural beams, a shutter backdrop, floor detail, shadows, crate fasteners and wheel rotation. Background props do not create new interactive systems. Reduced-motion preference disables engine vibration and UI transitions.

Validation: full automated keyboard route and both cargo recovery deliveries pass; 30/60/120 FPS simulation routes remain 11.500 seconds. Existing keyboard conflict, pause/reset and storage checks rerun. Added a result stats visibility/value assertion. Visually inspected the start, play and completion layouts at the normal 1265 × 712 viewport; the desktop play area and toolbar fit together. Inspected 390 × 844 responsive layout and fixed the lever keycaps wrapping. Temporary viewport restored. Result preview available in the local harness at checks.html?result. These are automated browser checks and visual inspection, not fresh human playtesting. No physics changes or M2 content; m1-2 records and notes remain compatible.

## 2026-09-13 — Stronger art direction: Night Shift

The previous polish pass was too subtle for the user. This pass changes the large visual masses: orange/black title treatment, ivory enamel console with orange and teal buttons, hazard strip, cream dialog cards, stronger amber light pools and a taller, rounded machine with a glazed cab, larger wheels and beacon. Cropped empty vertical workshop space from a 900×500 canvas to 900×360 while preserving the full horizontal lane; removed desktop letterboxing. Machine drawing rises 193 world units rather than 155, and gains additional displayed scale from using the scene width. All pickup, fork, bay and simulation coordinates are unchanged. Horn balloon flips left near the right edge to remain visible.

Validation: full keyboard route, both recovery deliveries, fixed-frame schedule comparisons, pause/reset, typing isolation and result statistics checks passed. Route remains 11.500 seconds at 30/60/120 schedules. Visually inspected desktop play, phone-width start/play (390×844), and full completion dialog; no new interactive background props. Restored temporary viewport. Checks are automated input replays plus visual inspection, not human feel or comprehension validation. Existing records/notes remain compatible with m1-2. No content beyond M1.
