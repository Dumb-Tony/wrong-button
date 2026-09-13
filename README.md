# Wrong Button — Night Shift

[Play Wrong Button](https://dumb-tony.github.io/wrong-button/)

Two machines, four jobs each. Learn the forklift, finish its challenge, then switch to a magnetic overhead gantry. The second chapter introduces precise magnetic coupling, detachable steel loads and dividers that require vertical clearance.

**Controls:** 1 / 2 / 3 press the matching controls. Left / Down / Right select the lever position. Hold Space for the bottom control. Escape pauses; R offers reset; J opens the job board. Mouse controls also work. All eight jobs are open from the start for feedback.

Power, brake and hoist retain their relationships. The gantry's square teal control replaces the forklift horn with a magnetic switch. The machine announcement, scene, panel shape, observations and hints reflect the change.

Notes, best times and settings save locally. Notes and sound migrate from the earlier campaign or M1. Old times remain in their original storage: reordered jobs and different machines do not share records. No deadlines, accounts or online dependencies.

**Offline:** `game/index.html` contains all CSS, JavaScript, Canvas artwork and generated audio. Direct file opening has not been verified by the restricted browser tool. The [original one-job prototype](https://dumb-tony.github.io/wrong-button/classic/) remains available.

**Developer checks:** serve `game` with a static server and visit `checks.html`. The suite solves all eight jobs at 30/60/120 frame schedules and replays the complete campaign through the keyboard handlers. It tests obstacles, dropped-load recovery, power loss, inspection, parking, navigation and save migration. These are automated replays, not human feel testing. Run on a separate test origin because replaying creates local records.

- [Campaign rules and jobs](docs/CAMPAIGN.md)
- [Actual test evidence](docs/PLAYTEST_LOG.md)
- [Original design](GDD.md)

GitHub Pages publishes only the current game and classic HTML. Private source transcripts remain local and excluded from Git.
