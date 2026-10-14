---
type: mobile-app
actors:
  - user
entryPoints:
  - mobile-app: timetracking://nfc
references:
  - kind: code
    role: implementation
    target: src/app/_layout.tsx#RootLayout
  - kind: code
    role: implementation
    target: src/plugins/withNfcIntent.ts#withNfcIntent
  - kind: code
    role: implementation
    target: src/services/QuickActionService.ts#initQuickActions
  - kind: doc
    role: intent
    target: README.md
    title: README
---

# Mobile app

The Android and iOS app. Besides its own views it is reached through an NFC tag the app has written (the tag opens the app's check-in link), through the "Check-In / Out" quick action on the app icon, and, in the standard build, through background location monitoring that checks the User in and out at the working location.
