# Generated Flutter structure

Generate this contract under target `apps/mobile/`. Feature names and optional platform
capabilities come from reconciled requirements.

```text
apps/mobile/
├── pubspec.yaml
├── pubspec.lock
├── analysis_options.yaml
├── .env.example
├── .gitignore
├── README.md
├── android/
├── ios/
├── assets/
│   ├── images/
│   └── fonts/
├── lib/
│   ├── main.dart
│   ├── app/
│   │   ├── app.dart
│   │   ├── bootstrap.dart
│   │   └── router.dart
│   ├── core/
│   │   ├── config/env.dart
│   │   ├── errors/app_failure.dart
│   │   ├── network/api_client.dart
│   │   ├── network/api_error.dart
│   │   ├── security/secure_storage.dart
│   │   └── theme/app_theme.dart
│   ├── features/
│   │   └── <feature>/
│   │       ├── data/
│   │       ├── domain/
│   │       ├── application/
│   │       └── presentation/
│   ├── shared/
│   │   └── widgets/
│   └── l10n/
│       └── app_en.arb
├── test/
│   ├── helpers/
│   └── goldens/
└── integration_test/
    └── app_test.dart
```

Generation order:

Realtime features conditionally add `lib/core/realtime` transport/event/state boundaries plus unit
and integration tests. They handle Android/iOS lifecycle, network state, bounded retry, cursor
resync, deduplication, and offline push without coupling sockets to widgets.

Naming and growth rules:

- Build a feature map from PRD journeys, screens, entities, and API resources. Preserve clear PRD
  product terms; when a capability is unnamed, use familiar names such as `authentications`,
  `accounts`, `notifications`, `articles`, `tasks`, `webhooks`, or `chat`.
- Do not invent `identity`, `work`, `operations`, `data`, `management`, or `collaboration` features
  unless the PRD intentionally names them. Use snake_case feature directories and Dart files.
- Name pages, widgets, controllers/notifiers, use cases, repositories, data sources, DTOs, and tests
  after their product responsibility—for example `sign_in_page.dart`, `task_list_controller.dart`,
  and `create_task.dart`. Avoid generic `screen.dart`, `widget.dart`, `manager.dart`, or `helper.dart`.
- Keep each feature layer cohesive and each source file at most 250 lines. Split presentation into
  pages/widgets, application state by use case, and data/domain code by resource while preserving
  Android/iOS lifecycle, navigation, accessibility, and tests.

1. Resolve supported Flutter/Dart, package, Android, and iOS constraints.
2. Create native projects with non-secret identifiers and environment boundaries.
3. Establish strict analysis, app assembly, navigation, theme, localization, and tests.
4. Create typed network, error, and secure-storage boundaries from approved contracts.
5. Produce the PRD-to-feature map, then generate only requirement-backed features.
6. Add unit, widget, golden, integration, accessibility, and lifecycle tests.
7. Verify Android and available iOS release builds before target-owned CI delivery.
