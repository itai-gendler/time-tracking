---
entities:
  - entity: working-location
    shows:
      - Position
      - Radius
    collects:
      - Position
      - Radius
references:
  - kind: code
    role: implementation
    target: src/screens/menu/GeofenceSetupScreen.tsx#GeofenceSetupScreen
---

# Working Location

The map on which the User places the working location and its radius, with the switch for automatic check-in. Only in the standard build.
