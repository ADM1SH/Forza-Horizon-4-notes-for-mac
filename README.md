# Forza Horizon 4 notes for Mac

Own notes on Forza Horizon 4 (Steam) on Apple Silicon through CrossOver and Apple D3DMetal. This repo holds notes only. It holds no patches, no binaries and no files of other projects.

Status on 12/11/2026: the FH4 patches of a third-party project are installed in the `Steam` bottle of the test Mac. No FH4 result is recorded here since the CrossOver changes of 05/11/2026 to 11/11/2026. Adam reports that FH4 works with those patches (user-reported, no log yet). See research.md.

## Scope

- Notes on what is installed, what changed and what is proven.
- How FH4 and FH5 share one CrossOver install on the same Mac.
- Out of scope: cracks, DRM removal, license bypass, Steam emulators, fake AppIDs, DLC unlocks, achievement emulation.

## Install

This repo has no install guide. The patches come from a third-party project: https://github.com/whyAm-i/Forza-Horizon-4-patches-for-mac. This repo does not test it, does not vouch for it and does not copy any of its files. The project has no license file (decisions.md, D-001). Read its README and scripts before you run anything.

## Files

| File | Purpose |
|---|---|
| research.md | What is installed, what is proven, what is unknown |
| prd.md | What this repo does and does not do |
| implementation_plan.md | Phases |
| task_today.md | The next task |
| testing.md | Test cases |
| bugs.md | Open and fixed bugs |
| audit.md | Release checklist status |
| decisions.md | Numbered decisions and open questions |
| ARCHITECTURE.md | Code layout (none yet) |
| CODE_STYLE.md | Code rules (none yet) |
| SECURITY.md | Secrets, logs and report rules |
| CONTRIBUTING.md | How to contribute |
| handoff.md | Session state |

## License

MIT. See LICENSE. It covers the text in this repo only.
