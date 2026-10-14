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

# Disable auto check-in

Turn off automatic check-in and check-out; the Product stops watching the working location. Only in the standard build.
