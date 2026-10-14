---
scope: 'The Time Tracking app: its views, menu pages, services, local storage, CSV handling and translations.'
method: Static reading of the source, tests and store metadata at the pinned commit; nothing was run.
covered:
  - description: App routes, root layout and the Day, Week and Month views with their entry list.
    paths:
      - src/app/
      - src/screens/HomeScreen.tsx
      - src/screens/DayView.tsx
      - src/screens/WeekView.tsx
      - src/screens/MonthView.tsx
      - src/components/EventListItem.tsx
      - src/components/TimeSeparator.tsx
      - src/components/EmptyState.tsx
      - src/components/AdaptiveDateTimePicker.tsx
  - description: Menu drawer, settings, language, working location and NFC setup pages.
    paths:
      - src/components/MenuDrawerContent.tsx
      - src/screens/settings/
      - src/screens/menu/GeofenceSetupScreen.tsx
      - src/screens/menu/GeofenceSetupScreen.foss.tsx
      - src/screens/menu/NFCSetupScreen.tsx
  - description: Local storage, balance arithmetic, date helpers and CSV import and export.
    paths:
      - src/db/
      - src/utils/
      - src/types.d.ts
  - description: Background location task, NFC link handling and app-icon quick action.
    paths:
      - src/services/
      - src/plugins/withNfcIntent.ts
  - description: Translations and language selection.
    paths:
      - src/i18n/
  - description: Build configuration that switches between the standard and FOSS builds.
    paths:
      - app.config.ts
      - metro.config.js
      - tsconfig.foss.json
exclusions:
  - description: Theme provider for light, dark and dynamic colors.
    paths:
      - src/context/
  - description: Build plugins that strip permissions and dependency metadata.
    paths:
      - src/plugins/withRemovePermissions.ts
      - src/plugins/withDisableDependencyMetadata.ts
  - description: Test setup, CI workflows and release tooling.
    paths:
      - src/test/
      - .github/
  - description: Store listings, screenshots, icons and agent instructions.
    paths:
      - metadata/
      - docs/
      - assets/
      - .agents/
unmapped:
  - description: Licenses and Privacy Policy pages with fixed text.
    paths:
      - src/screens/menu/LicensesScreen.tsx
      - src/screens/menu/PrivacyPolicyScreen.tsx
limitations: []
---

# Coverage
