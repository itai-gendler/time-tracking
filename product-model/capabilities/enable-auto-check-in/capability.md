---
domain: working-location
availability:
  - place: mobile-app
references:
  - kind: code
    role: implementation
    target: src/screens/menu/GeofenceSetupScreen.tsx#GeofenceSetupScreen
  - kind: doc
    role: intent
    target: README.md
    title: README
  - kind: code
    role: implementation
    target: src/services/LocationTask.ts#LOCATION_TASK_NAME
---

# Enable auto check-in

Turn on automatic check-in and check-out at the working location. The Product then records a check-in when the phone enters the area and a check-out when it leaves. It needs a working location and the phone's permission to use the location in the background. Only in the standard build.
