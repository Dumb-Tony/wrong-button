# Wrong Button — Night Shift

[Play the 24-job campaign](https://dumb-tony.github.io/wrong-button/)

One machine. Five controls that never shuffle. Twenty-four authored jobs across four shifts, combining deliveries, reverse journeys, precision bays, height-sensor passages, horn-operated doors, inspection stamps, multiple lettered crates and parking objectives.

**Controls:** 1 / 2 / 3 press the matching controls. Left / Down / Right select the lever position. Hold Space for the bottom control. Escape pauses; R offers reset; J opens the job board. Mouse controls also work. The job board is available from the start and pause screens, and every job is open for feedback.

Progress, per-job best times, notes and sound preference save locally. Existing M1 notes/sound migrate; its times remain separate because the campaign has different rules. Finished cargo stays delivered for the attempt. No timer failures, accounts or online requirements.

**Offline:** open `game/index.html` directly. It contains its own CSS, JavaScript, Canvas artwork and generated audio. Direct file opening has not been verified by the restricted browser tool. The [original one-job prototype](https://dumb-tony.github.io/wrong-button/classic/) remains available, with its source untouched in `prototypes/m1`.

**Developer checks:** serve `game` with any static server, then visit `checks.html`. The suite solves all 24 jobs at three frame schedules and replays the entire campaign through the keyboard handlers. It also checks obstacle rejection, inspections, parking, navigation and save behavior. It uses a virtual clock and test-owned input, not human playtesting. The local test origin can acquire test records; use a separate profile if preserving local practice records matters.

- [Campaign rules and job list](docs/CAMPAIGN.md)
- [Actual test evidence and remaining gates](docs/PLAYTEST_LOG.md)
- [Original design](GDD.md)

GitHub Pages publishes only the campaign HTML and classic HTML. Private source transcripts remain local and excluded from Git.
