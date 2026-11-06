# Docs version updater

Once a week this checks the software facts in the lab's docs repositories (versions, release and end-of-life dates, supported platforms, install and CLI commands) against current primary sources and opens a pull request with any corrections. Claude (`claude-opus-5-5`, effort `medium`) does the checking with web search and web fetch. It edits only the page it was given, cites a source for every change, and leaves lab facts and `[placeholders]` alone.

## How it runs

| Piece | Where |
| --- | --- |
| The checker | `tools/docs-version-updater/updater.py` in this repository |
| Reusable workflow | `.github/workflows/docs-version-updater.yml` in this repository |
| Weekly callers (Mondays, 12:00 UTC) | `.github/workflows/version-check.yml` in getting-started-atr-lab, all-things-ros2 and dev-guidelines |
| API key | Repository secret `ANTHROPIC_API_KEY_ATR_LAB_DOC_UPDATER` in each calling repository |

For each page the workflow:

1. Starts a conversation with Claude that holds the repository's `AGENTS.md` (its writing and sourcing rules) and the page.
2. Lets Claude search the web, fetch release notes and docs, read other pages in the repository, and change the page through an `edit_page` tool. An edit is refused unless its old text appears exactly once, it keeps every `[placeholder]` and it gives an `https://` source.
3. Sets the page's "Last reviewed" footer to the run date if anything changed.

Then it runs markdownlint and the lab brand check on each changed page and drops the changes to any page that fails. Whatever is left goes into one pull request on the branch `automation/version-updates`. The PR body lists every change with its sources and the run's estimated API cost. A later run updates the same pull request until someone merges or closes it.

Pull requests opened by GitHub Actions don't start the repository's own CI. Push a commit to the branch, or close and reopen the pull request, to run it before you merge.

## Run it by hand

From a calling repository's **Actions** tab, run **version-check** and, optionally, give it a narrower glob (for example `tech-stack/gazebo.md`) or a page limit. Locally, from the root of a docs repository:

```bash
python3.12 -m venv .venv && .venv/bin/pip install -r path/to/tools/docs-version-updater/requirements.txt
ANTHROPIC_API_KEY=... .venv/bin/python path/to/tools/docs-version-updater/updater.py --paths "tech-stack/gazebo.md"
```

It edits the pages in place and writes `version-update-report.md`; review with `git diff`.

## Change it

- **Which pages:** the `paths` line in each caller's `version-check.yml`.
- **Model, effort, search limits:** the constants at the top of `updater.py`. The prices there only feed the report's cost estimate.
- **What Claude is told:** `INSTRUCTIONS` in `updater.py`. Each repository's `AGENTS.md` is sent with it, so writing rules belong there.
- **Style:** the lab's Python guide; `ruff.toml` here is a copy of `dev-guidelines/configs/python/ruff.toml`. Run `ruff format` and `ruff check` before you commit.
