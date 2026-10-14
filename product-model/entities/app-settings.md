---
singleton: true
domain: settings
references:
  - kind: code
    role: implementation
    target: src/screens/settings/LanguageSettingsScreen.tsx#LanguageSettingsScreen
  - kind: code
    role: implementation
    target: src/i18n/i18n.ts#initI18n
---

# App settings

The preferences the app keeps once per installation.

## Information kept

- **Language** — Automatic (System), English or German; Automatic until changed. Automatic uses German when the phone's language is German and English otherwise
