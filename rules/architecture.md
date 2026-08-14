# Architecture rules

- Generate mobile source only in target `apps/mobile/`.
- Keep application assembly, core capabilities, shared UI, and feature boundaries explicit.
- Separate domain behavior from widgets, plugins, persistence, and transport.
- Consume typed API adapters and validate untrusted network and persisted data.
- Make navigation, lifecycle, offline, loading, empty, failure, and retry states explicit.
- Support Android and iOS from one codebase while preserving platform conventions.
