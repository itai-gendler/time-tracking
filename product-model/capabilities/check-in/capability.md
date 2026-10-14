---
domain: day
availability:
  - place: mobile-app
references:
  - kind: code
    role: implementation
    target: src/screens/DayView.tsx#DayView
  - kind: code
    role: implementation
    target: src/services/NFCService.ts#initNfcService
  - kind: code
    role: implementation
    target: src/services/QuickActionService.ts#initQuickActions
  - kind: code
    role: implementation
    target: src/services/LocationTask.ts#LOCATION_TASK_NAME
  - kind: doc
    role: intent
    target: README.md
    title: README
---

# Check in

Start a working session now by recording a check-in at the current time. It is offered on today's Day view while the User is not working, by holding the phone to an NFC tag the app has written, by the "Check-In / Out" quick action on the app icon, and, in the standard build while auto check-in is on, automatically when the phone enters the working location.
