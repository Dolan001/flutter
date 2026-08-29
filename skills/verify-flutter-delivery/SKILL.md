---
name: verify-flutter-delivery
description: Independently verify affected Flutter features or mobile delivery against requirements, approved design, Android behavior, iOS behavior, security, tests, and release-readiness evidence.
---

# Verify Flutter delivery

Inspect the diff and run formatting, static analysis, affected unit and widget tests,
goldens, integration journeys, and available Android/iOS release builds. Verify
accessibility, text scaling, localization, responsive layout, lifecycle restoration,
network failure, offline behavior, secure storage, permissions, dependency risk, and
secret absence. Capture exact platform limitations and evidence; do not edit source.
Independently validate feature names against the PRD/fallback policy, responsibility-based Dart
filenames, layered ownership, and the 250-line split limit.

Reuse a passing shared full-matrix report only when its revision and workspace inputs
still match, then run focused changed-slice checks. Do not rerun every Android/iOS and
integration lane per feature. For design fidelity, act independently from the resolver
and write the final `verification.json`; resolver evidence cannot approve its own repair.

Apply `../implement-flutter-vertical-slice/references/production-delivery.md` from a
clean verification context and compare against approved HTML/screenshots, not memory.
