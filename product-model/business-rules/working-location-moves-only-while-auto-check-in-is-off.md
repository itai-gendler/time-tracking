---
appliesTo:
  - type: entity
    id: working-location
    effect: changes
    facts:
      - Position
      - Radius
permits:
  - actors:
      - user
    when:
      - state: Auto check-in off
references:
  - kind: code
    role: implementation
    target: src/screens/menu/GeofenceSetupScreen.tsx#GeofenceSetupScreen
---

# The User changes the position and radius of the working location only while auto check-in is off

While auto check-in is on, a new position or radius is shown on the map but not applied: the Product keeps watching the previous area and asks the User to turn auto check-in off and on again.
