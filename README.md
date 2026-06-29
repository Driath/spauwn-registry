# Spauwn Registry

Public registry for installable Spauwn artifacts.

The registry is catalogue truth, not runtime truth. Spauwn fetches this repo,
checks out the latest SemVer tag, reads `index.json`, then proposes installs.
Active config remains local under `~/.spauwn`.

## Artifacts

- `gambit-pack`: routing presets copied into `~/.spauwn/gambits/`
- `skill`: agent-facing skills copied or linked into local skill locations
- `theme`: visual themes copied into local theme storage

## Rules

- No artifact is auto-installed.
- No remote content is executed directly.
- Install destinations are relative to `~/.spauwn`.
- Updates require user review.

