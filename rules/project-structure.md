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

1. Resolve supported Flutter/Dart, package, Android, and iOS constraints.
2. Create native projects with non-secret identifiers and environment boundaries.
3. Establish strict analysis, app assembly, navigation, theme, localization, and tests.
4. Create typed network, error, and secure-storage boundaries from approved contracts.
5. Generate only requirement-backed features using recorded state conventions.
6. Add unit, widget, golden, integration, accessibility, and lifecycle tests.
7. Verify Android and available iOS release builds before target-owned CI delivery.
