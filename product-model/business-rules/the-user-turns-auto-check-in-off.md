---
appliesTo:
  - type: entity
    id: working-location
    effect: changes
    to: Auto check-in off
permits:
  - actors:
      - user
references:
  - kind: code
    role: implementation
    target: src/screens/menu/GeofenceSetupScreen.tsx#GeofenceSetupScreen
---

# The User turns auto check-in off at any time

Turning automatic check-in off needs nothing beyond the switch; the working location stays saved.
