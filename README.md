# Flutter behavior pack

This repository supplies Flutter-specific guidance to the [agents workflow](https://github.com/Dolan001/agents).
It is not a generated mobile app. The workflow writes the real Android/iOS project into the user's
`apps/mobile/` directory.

## When to use it

Declare `Mobile framework: Flutter` in the PRD. The `flutter` pack is selected automatically,
together with the chosen DRF or FastAPI backend pack. `$start-build` runs every applicable phase;
to stop after the mobile gate, use:

```bash
./.agents/bin/ai start-mobile --project . --github-user <your-github-user>
```

The PRD or saved state supplies Flutter, so `--mobile flutter` is optional when already declared.
Mobile implementation uses approved design and verified API contracts. No command pushes by
default.

## What it creates and verifies

The target app has Android and iOS platform projects, feature-oriented Dart code, typed API access,
explicit loading/error/offline states, accessibility and text-scaling behavior, and tests.
Realtime support is added only when the PRD needs it.

The independent gate checks Flutter analysis and tests, structure, platform readiness,
approved-design semantics, accessibility, and live API integration. If iOS tooling is unavailable
on the current machine, that claim stays unverified. Check `.ai/` evidence and `$workflow-status`
for the exact resume point.

## Pack contents

`agents/` defines mobile roles; `skills/` covers inspection, app creation, feature slices,
realtime, and verification; `rules/`, `hooks/`, and `commands/` constrain work. No app source,
dependency cache, build output, or signing material belongs in this behavior repository.
