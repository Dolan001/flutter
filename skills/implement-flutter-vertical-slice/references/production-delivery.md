# Flutter production delivery

## Architecture and state

- Keep feature data, domain, application, and presentation boundaries explicit.
- Keep domain logic independent of widgets, Flutter bindings, plugins, and transport.
- Select one maintained state approach from project constraints; do not mix patterns
  without a recorded boundary.
- Model immutable state and typed events/results. Make cancellation and concurrency
  behavior explicit.
- Keep navigation typed, deep-linkable, guarded, and restorable where required.

## API, persistence, and offline behavior

- Consume the backend contract through typed adapters; validate untrusted payloads at
  runtime and map transport failures to stable domain failures.
- Define timeout, cancellation, retry, idempotency, pagination, refresh, and token
  renewal behavior. Never retry unsafe writes implicitly.
- Store credentials only through platform-secure storage. Keep secrets, signing keys,
  and production endpoints out of source and compiled public configuration.
- Version local schemas and migrations. Define cache ownership, freshness, encryption,
  conflict resolution, and offline state when persistence is required.

## Android and iOS

- Use stable supported Flutter/Dart and plugin versions with a committed lockfile.
- Configure unique application identifiers, minimum supported OS versions, flavors,
  universal/app links, icons, launch assets, and permissions from requirements.
- Request permissions at point of use, explain denial, and handle restricted settings.
- Keep native customization minimal, documented, and symmetric where capability allows.
- Handle foreground/background transitions, process death, interrupted authentication,
  deep links, network changes, and state restoration.
- Never commit keystores, certificates, provisioning profiles, credentials, or tokens.

## Design, accessibility, and localization

- Translate approved design semantics into adaptive Material/Cupertino behavior without
  forcing one platform's interaction conventions onto the other.
- Support small phones, large phones, tablets, orientation constraints, safe areas,
  keyboard insets, and configured text scaling.
- Provide semantic labels, traversal order, sufficient contrast, non-color cues,
  reduced motion, large touch targets, and screen-reader announcements.
- Externalize user-facing text, support pluralization and layout direction, and test
  representative long translations and right-to-left layout when required.

## Performance and reliability

- Avoid unbounded rebuilds, blocking the UI isolate, oversized images, leaked
  controllers/subscriptions, and unbounded lists or caches.
- Profile startup, frame rendering, memory, network volume, battery-sensitive work,
  and application size where acceptance criteria require budgets.
- Use structured privacy-safe logging and crash reporting boundaries. Do not log
  credentials, personal data, authorization headers, or full sensitive payloads.

## Verification and release

- Run `dart format`, `flutter analyze`, unit, widget, and affected integration tests.
- Use deterministic golden tests for stable visual surfaces; review intentional updates.
- Exercise loading, empty, validation, offline, timeout, server error, authorization,
  background/resume, deep link, and retry paths.
- Verify Android release output and iOS no-codesign release output on capable hosts.
  Record an unavailable platform as unverified rather than claiming success.
- Audit dependencies, licenses, permissions, exported Android components, iOS usage
  descriptions, network security configuration, debug flags, and secret scans.
- Keep store publishing, signing, rollout, and production deployment behind explicit
  human authorization.
