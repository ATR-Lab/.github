# Contributing to ATR-Lab repositories

> **Read this when** you want to change code or docs in any repository of the Advanced Telerobotics Research Lab
> at Kent State University. A repository with its own `CONTRIBUTING.md` overrides this page.

Thank you for helping. Lab members and outside contributors follow the same short process: talk first, change
one thing per pull request, and leave the repository easier to use than you found it.

## Before you start

1. **Look for an existing issue**, or open one that describes the problem or the idea. For a typo or a broken
   link, go straight to a pull request.
2. **Read the repository's `README.md` and `AGENTS.md`.** `AGENTS.md` lists the files, the sources of truth and the
   checks that repository expects.
3. **Follow the lab's code style.** The [dev guidelines](https://github.com/ATR-Lab/dev-guidelines) have style
   guides and copy-ready lint configs for six languages: C and C++; Swift; Kotlin; C# and Unity; Python;
   JavaScript and TypeScript.

## Making a change

1. Create a branch from the default branch: `feature/<short-name>`, `fix/<short-name>` or `docs/<short-name>`.
2. Keep commits small and write messages that follow the
   [seven rules of a great commit message](https://github.com/ATR-Lab/dev-guidelines/blob/master/docs/git-and-github.md).
3. Build, test and lint before you push. The checks each repository runs are in its `AGENTS.md`.
4. Open a pull request. Fill in the template, link the issue (`Closes #12`) and ask for a review.
5. Address review comments with new commits; the reviewer merges when the checks pass.

## Rules that apply everywhere

- **Never commit secrets:** passwords, API keys, tokens, robot Wi-Fi credentials or `.env` files. If one slips
  in, tell a maintainer right away; deleting it in a later commit does not remove it from history.
- **Never commit research data about people:** study recordings, consent forms or anything that identifies a
  participant. Human-subjects data stays in the storage your IRB protocol names.
- **Large files** (meshes, bags, datasets, model weights) go through Git LFS or external storage, not plain Git.
- **AI coding assistants** (Claude Code, Codex and others) are welcome. You are responsible for every line they
  write: review the diff, run the tests and follow the
  [lab's rules for AI-assisted development](https://github.com/ATR-Lab/dev-guidelines/blob/master/docs/ai-assisted-development.md).
- **Label robot videos** in pull requests and docs: teleoperated, autonomous, semi-autonomous or scripted, and
  the playback speed.

## Licensing of contributions

By contributing, you agree that your contribution is released under the license of the repository you are
contributing to. The names and logos of the Advanced Telerobotics Research Lab and Kent State University are
trademarks and are not covered by any repository license.

## Code of conduct

Everyone who takes part in ATR-Lab repositories follows the [code of conduct](CODE_OF_CONDUCT.md). Lab members
also follow the [lab's own code of conduct](https://github.com/ATR-Lab/getting-started-atr-lab/blob/master/lab-rules/code-of-conduct.md).

## Questions

See [SUPPORT.md](SUPPORT.md) for where to ask.

<sub>Last reviewed: Sept. 30, 2026</sub>
