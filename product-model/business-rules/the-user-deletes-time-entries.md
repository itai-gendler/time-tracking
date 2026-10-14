---
appliesTo:
  - type: entity
    id: time-entry
    effect: removes
permits:
  - actors:
      - user
references:
  - kind: code
    role: implementation
    target: src/screens/HomeScreen.tsx#HomeScreen
---

# The User deletes any time entry the app keeps

Every entry belongs to the one User of the installation, whichever way it was recorded, and deleting it needs only the User's confirmation.
