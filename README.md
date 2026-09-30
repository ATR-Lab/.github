<p align="center">
  <img src="profile/assets/header.png" alt="Advanced Telerobotics Research Lab, Department of Computer Science, Kent State University." width="100%">
</p>

<p align="center">
  <b>The ATR-Lab organization's profile page and the default community files for every lab repository.</b><br>
  <sub>Advanced Telerobotics Research Lab · Department of Computer Science · Kent State University</sub>
</p>

<p align="center">
  <a href="LICENSE"><img alt="License: MIT" src="https://img.shields.io/badge/license-MIT-003976?style=flat-square"></a>
  <a href="https://www.atr.cs.kent.edu/"><img alt="Advanced Telerobotics Research Lab, Kent State University" src="https://img.shields.io/badge/ATR_Lab-Kent_State-003976?style=flat-square"></a>
  <img alt="Last reviewed Sept. 2026" src="https://img.shields.io/badge/last_reviewed-Sept._2026-4A5868?style=flat-square">
</p>

GitHub treats a repository named `.github` specially:

- **`profile/README.md` is the organization's front page.** It appears at the top of
  [github.com/ATR-Lab](https://github.com/ATR-Lab) for everyone.
- **The community files here are defaults for every ATR-Lab repository** that doesn't have its own:
  contributing guide, code of conduct, security policy, support page, issue forms and the pull request template.
  A repository that adds its own version of a file (or its own `.github/ISSUE_TEMPLATE/` folder) overrides the
  default.

## Repo map

| Path | What it is | Shows up |
|---|---|---|
| [`profile/README.md`](profile/README.md) | The organization's front page | github.com/ATR-Lab |
| `profile/assets/` | Header, social preview and icons used by the front page | Front page |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | How to contribute to any lab repository | "Contributing" link on every repo without its own |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md) | Community standards and how to report a problem | Every repo without its own |
| [`SECURITY.md`](SECURITY.md) | How to report a vulnerability privately | The "Security" tab of every repo without its own |
| [`SUPPORT.md`](SUPPORT.md) | Where to ask for help | Linked when people open an issue |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE) | Bug report, feature request and documentation fix forms | "New issue" on every repo without its own |
| [`.github/PULL_REQUEST_TEMPLATE.md`](.github/PULL_REQUEST_TEMPLATE.md) | The pull request checklist | Every new pull request |
| [`AGENTS.md`](AGENTS.md) | Map of the whole organization for coding agents | |

## Editing

- The front page must stay short: what the lab is, where to start, current work and links. Use only the
  verified facts and wording in the [ATR Lab design skill](https://github.com/ATR-Lab/atr-lab-design-skill)
  (`references/brand-foundation.md`).
- Images on the front page use absolute `raw.githubusercontent.com` URLs, because the organization page does not
  resolve relative paths. They appear once the change is merged into `main`.
- After editing, run the checks in [`AGENTS.md`](AGENTS.md#how-to-check-your-work).
- **Social preview:** upload `profile/assets/social-preview.png` in **Settings → General → Social preview**.

## Organization settings to fix by hand

These live in the organization's settings (**github.com/organizations/ATR-Lab/settings/profile**), not in files:

| Setting | Today | Change to |
|---|---|---|
| Display name | Missing the "s" in "Telerobotics" | Advanced Telerobotics Research Laboratory |
| Description | Mentions "+400 media outlets" | An innovation research laboratory at Kent State University exploring telepresence robotics, tele-embodiment, autonomy and artificial intelligence. |
| Location | Kent, Ohio, U.S.A | Kent, Ohio |
| Email | none | [a kent.edu lab address] |
| Avatar | | `atr-avatar-mark-navy.png` from the design skill (`assets/logos/icons/`) |

## License

Text and code in this repository are released under the [MIT License](LICENSE). The names and logos of the
Advanced Telerobotics Research Lab and Kent State University are trademarks and are not covered by that license.

---

<p align="center">
  <sub><b>ATR Lab docs</b> ·
  <a href="https://github.com/ATR-Lab/about">About the lab</a> ·
  <a href="https://github.com/ATR-Lab/getting-started-atr-lab">Getting started</a> ·
  <a href="https://github.com/ATR-Lab/dev-guidelines">Dev guidelines</a> ·
  <a href="https://github.com/ATR-Lab/all-things-ros2">All things ROS 2</a> ·
  <a href="https://github.com/ATR-Lab">All repositories</a></sub><br>
  <sub>Advanced Telerobotics Research Lab · Department of Computer Science · Kent State University ·
  <a href="https://www.atr.cs.kent.edu/">www.atr.cs.kent.edu</a></sub>
</p>
