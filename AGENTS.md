# AGENTS.md: ATR-Lab/.github

This is the special `.github` repository of the **ATR-Lab** GitHub organization, which belongs to the Advanced
Telerobotics Research Lab (Department of Computer Science, Kent State University). It holds the organization's
front page (`profile/README.md`) and the default community files that GitHub applies to every ATR-Lab repository
without its own. It is **not** where lab documentation lives; this file also serves as the map of the whole
organization, so start here when you need to know which repository answers a question.

## Organization map: which repository answers which question

| Question | Repository | Default branch |
|---|---|---|
| What is the lab, what does it research, what has it achieved, who is in it, where is the press kit? | [ATR-Lab/about](https://github.com/ATR-Lab/about) | `master` |
| I'm new: rules, safety, research standards, LaTeX templates, tech stack, lab hardware? | [ATR-Lab/getting-started-atr-lab](https://github.com/ATR-Lab/getting-started-atr-lab) | `master` |
| How should code look, which lint configs, Git and PR practice, rules for AI coding agents? | [ATR-Lab/dev-guidelines](https://github.com/ATR-Lab/dev-guidelines) | `master` |
| ROS 2 concepts, distributions (Foxy to Lyrical), installation, commands, debugging, lab robots in ROS 2? | [ATR-Lab/all-things-ros2](https://github.com/ATR-Lab/all-things-ros2) | `main` |
| Logos, colors, fonts, templates, brand and copy rules, verified lab facts? | [ATR-Lab/atr-lab-design-skill](https://github.com/ATR-Lab/atr-lab-design-skill) | `main` |
| Reproducible ROS 2 environments with lockfiles? | [MarcoDotIO/rosenv](https://github.com/MarcoDotIO/rosenv) (a lab member's project, outside the org) | `main` |

**Public project repositories** (many other lab repositories are private; don't name private ones in public
files):

| Platform or topic | Repositories |
|---|---|
| Unitree Go2 (quadruped) | `go2_ws` |
| Booster K1 (humanoid) | `expressive-motion` |
| SoftBank Pepper | `PepperKit`, `PepperLLMDemo`, `PepperLLMDemo-Server` |
| Coffee Buddy (service robot) | `kami-head` |
| Yahboom robots | `yahboom_r2l_ros2` |
| Robot mower | `robo_mower_ws` |
| TeleBot line (telepresence) | `TeleBot-4R`, `TeleBot-4R-XR` |
| Dynamixel servos | `multi-servo-dynamixel-library` |
| Other | `atr-dashboard`, `HRI-Tello-Drone-Controller`, `ATR-Lab.github.io` |

Check visibility before linking any other repository:
`gh repo view ATR-Lab/<name> --json visibility --jq .visibility`.

## Repo map (this repository)

| Path | Purpose |
|---|---|
| `profile/README.md` | Organization front page (keep it short; absolute image URLs) |
| `profile/assets/header.png` | 1600 × 400 front-page header, built from the design skill's poster band and the official lockup |
| `profile/assets/social-preview.png` | 1280 × 640 social preview (uploaded by hand in Settings) |
| `profile/assets/icons/` | 96 px navy icon badges from the design skill, used in the "Start here" grid |
| `README.md` | Explains this repository and the organization settings to fix by hand |
| `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `SUPPORT.md` | Org-wide default community files |
| `.github/ISSUE_TEMPLATE/` | Default issue forms (`bug_report.yml`, `feature_request.yml`, `docs_fix.yml`) and `config.yml` |
| `.github/PULL_REQUEST_TEMPLATE.md` | Default pull request template |
| `.github/workflows/docs.yml` | Markdown lint and link check for this repository only |
| `.markdownlint.jsonc` | Markdown lint rules shared by all lab docs repositories |
| `.lycheeignore` | Sites that block automated link checkers (check those links by hand) |
| `AGENTS.md`, `CLAUDE.md` | This file; `CLAUDE.md` imports it |
| `LICENSE` | MIT |

## Sources of truth

- **Lab facts** (names, director, projects, platforms, achievements and their exact wording, contacts, handles):
  only `references/brand-foundation.md` in the ATR Lab design skill (installed locally at
  `~/.claude/skills/atr-lab-design/`). Never invent names, rooms, results, dates or numbers; write a
  `[bracketed placeholder]` and list it under "Open items".
- **Never print** anything on the "Never print" list in `brand-foundation.md` §11 (a nonexistent social handle,
  the director's office room and phone as the lab's, an outdated college name, "KSU" in running copy, "ATR"
  alone, RoboCup placements, media-outlet counts). The brand check below catches most of these.
- **GitHub behavior** (community health files, issue forms, profile READMEs): docs.github.com.

## Writing rules

- Kent State style: sentence-case headings, no Oxford comma, "and" not "&", dates like "Sept. 30, 2026", no emoji.
- The lab's name: "Advanced Telerobotics Research Lab" on first reference, then "the lab"; "ATR Lab" only in
  display text, always with Kent State nearby.
- "ROS 2", never "ROS2", in prose. Cut hype words (cutting-edge, state-of-the-art, innovative, leverage, robust).
- Default community files apply to about 100 repositories: keep them general, short and free of lab-only
  details that could go stale.
- Issue forms must stay valid against GitHub's issue-forms schema.

## How to check your work

```bash
# Brand, facts and Kent State style (exit code 0 means no errors)
PYTHONDONTWRITEBYTECODE=1 ~/.claude/skills/atr-lab-design/.venv/bin/python ~/.claude/skills/atr-lab-design/scripts/brand_check.py $(git ls-files --cached --others --exclude-standard '*.md')
# Markdown structure
npx --yes markdownlint-cli2 "**/*.md"
# Issue forms parse as YAML
uvx --with pyyaml python -c "import glob, yaml; [yaml.safe_load(open(f)) for f in glob.glob('.github/ISSUE_TEMPLATE/*.yml')]"
```

## Open items

| Where | Placeholder | Who can fill it |
|---|---|---|
| `CODE_OF_CONDUCT.md` | `[conduct contact email]`, `[conduct contact role]`; the page is a draft until the director approves | Director |
| `SECURITY.md` | `[security contact email]` | Director or lab manager |
| `SUPPORT.md` | `[Slack channel]` | Lab manager |
| `README.md` (org settings table) | `[a kent.edu lab address]` | Director |
| Organization settings | Display name, description, location, email and avatar (see `README.md`) | An org owner |

## Related repos

- [about](https://github.com/ATR-Lab/about): what the lab is, research, achievements, press kit, members.
- [getting-started-atr-lab](https://github.com/ATR-Lab/getting-started-atr-lab): onboarding, rules, safety, research standards, tech stack, hardware.
- [dev-guidelines](https://github.com/ATR-Lab/dev-guidelines): code style, lint configs, Git, AI-assisted development.
- [all-things-ros2](https://github.com/ATR-Lab/all-things-ros2): the lab's ROS 2 handbook.
