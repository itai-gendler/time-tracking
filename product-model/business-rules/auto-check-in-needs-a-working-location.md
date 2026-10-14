---
appliesTo:
  - type: entity
    id: working-location
    effect: changes
    to: Auto check-in on
permits:
  - actors:
      - user
    when:
      - fact: Position
        present: true
references:
  - kind: code
    role: implementation
    target: src/screens/menu/GeofenceSetupScreen.tsx#GeofenceSetupScreen
---

# The User turns auto check-in on only once the working location has a position

Without a position the switch is refused with a request to long-press the map; the phone must also allow background location.
