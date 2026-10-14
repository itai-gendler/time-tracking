---
domain: settings
availability:
  - place: mobile-app
references:
  - kind: code
    role: implementation
    target: src/screens/settings/SettingsScreen.tsx#SettingsScreen
  - kind: code
    role: implementation
    target: src/db/database.ts#setDailyTargetMinutes
  - kind: code
    role: implementation
    target: src/utils/workHours.ts#resolveDailyTarget
  - kind: doc
    role: context
    target: metadata/en-US/changelogs/241.txt
    title: 'Release notes: different working hours'
---

# Change the daily work hours

Set the hours and minutes expected on each working day, on the Settings page. The new target applies from today onward; earlier days keep the target that applied to them. Until the User changes it, the target is 8 hours.
