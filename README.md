# Wrong Button

[Play the M1 prototype](https://dumb-tony.github.io/wrong-button/)

One unfamiliar machine, five unlabeled controls, one crate. Learn through experimentation, then retry from memory. Single player; M1 only. Human comprehension and enjoyment gates remain open.

Open `prototypes/m1/index.html` directly in a browser for offline play. No installation, build, CDN or external assets. The same single file is published by GitHub Pages. Browser storage saves only your notes, sound preference, reset count and compatible local records; gameplay works without storage.

For development, serve `prototypes/m1` with any static server and open `checks.html` to run the browser-based regression suite. The harness uses a virtual frame clock and synthetic DOM events; it is not a human playtest. Node is not required.

- [Design](GDD.md)
- [M1 scope and human acceptance gates](docs/PROTOTYPE_M1.md)
- [Transition table and tuning decisions — spoilers](docs/TRANSITIONS_M1.md)
- [Actual validation evidence and limitations](docs/PLAYTEST_LOG.md)

Private conversation source notes remain local and are excluded from Git. Deployment stages only the game HTML, not project notes or the regression harness. No M2 work is authorized by an automated test pass.

Keyboard: **1 / 2 / 3**, **Left / Down / Right**, and **hold Space** match the panel keycaps. No tabbing between machine controls is necessary. Press Enter to start/retry, Escape to pause, R to offer reset.
