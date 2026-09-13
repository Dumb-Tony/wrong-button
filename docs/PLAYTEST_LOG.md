# Wrong Button — Playtest log

## 2026-09-13 — M1, rules m1-1

Decision: **iterate / recruit fresh testers**. The bounded prototype is implemented. M1 comprehension, replay learning and interest gates are NOT passed. No M2 work began.

Hardware: AMD Ryzen 9 9950X 16-Core Processor; Windows reports AMD Radeon RX 9070 XT and AMD Radeon integrated graphics. Browser: Codex in-app Chromium; exact browser version and physical display resolution unavailable through this session. Captured viewport: 1265 × 712. GPU actually used by the browser was not measured.

Automated evidence (prototypes/m1/checks.html): start/play/result/restart; all actuator dependencies under power off; powered brake denial; braking while moving; 20 resets with fixed mappings and preserved notes; full pickup / ramp traversal / platform set-down / one-second settling route; focus-loss pause and held-input clear; no paused-time catch-up; recovery pickup from left and right; hovering crate rejected; one-hour simulated boundary soak; self-contained source check. Scripted route time was 11.500 seconds at each of 30, 60 and 120 render schedules (0% difference). These are virtual-clock tests, not measured novice/replay times. Synthetic keyboard events cover hold/release; ordinary button clicks model native activation. This does not establish a complete human keyboard-only route.

Browser interaction: actual Enter started the game and toggled the first button; Tab navigation reached the switch; Space released it, verified in the accessibility tree. Desktop screenshot inspected: readable scene, large control targets, visible ramp and marked bay. Developer readout sampled about 175.8 rendered FPS with frame cost rounded to 0.00 ms; that is one sample on this high-refresh host, not a sustained performance benchmark or a guarantee for other hardware. The fixed-clock regression provides independent simulation-repeatability evidence.

Tuning: broad symmetric carriage with 76-unit pickup reach, 100-unit/s travel, 65-unit/s lift, 40-unit/s lowering and immediate braking. These prioritize observation and forgiving recovery. No destructive drop states or random failures. One observational hint only. See TRANSITIONS_M1.md for full transition table and rationale.

Limitations: no fresh human testers, no subjective feel testing, no measured ten-minute novice gate, no after-break replay comprehension test, no interest-in-another-machine gate. Direct file:// navigation was blocked by the browser tool; the code is dependency-free but direct offline opening must still be checked in a normal browser. Node executable exited with no diagnostics, so tests run in the browser instead. Full human keyboard-only completion, mobile touch feel, screen-reader experience, sustained 60 FPS measurement and additional browser coverage remain open.

Next bounded experiment: give five fresh players only the objective and generic input instructions. Record mistaken hypotheses, first solve time, hint count, break/replay time, dependency explanations and voluntary interest. Require four solves within ten minutes with at most the observational hint; three replays under half the first time with correct explanations; three interested in another machine. If weak, tune feedback or friction before any new content.

Storage regression: explicitly throwing localStorage access still permits play and preserves in-memory notes across reset (PASS).
