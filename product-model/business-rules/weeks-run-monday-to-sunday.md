---
appliesTo:
  - type: capability
    id: view-week
    contexts:
      - place: mobile-app::week
references:
  - kind: code
    role: implementation
    target: src/screens/WeekView.tsx#WeekView
---

# A week runs from Monday to Sunday

The Week view and its balance always cover Monday to Sunday, whatever the phone's language or region.
