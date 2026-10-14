---
kind: validation
routes:
  app: Mobile app
steps:
  - text: The User picks a CSV file with no row that has both a date and a time and no valid work hours line
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
  - text: The Product says no importable data was found and imports nothing
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
---

# Refuse a CSV without importable data

## Trigger

The chosen file is empty, has only its header or comes from another app.

## Outcome

Nothing is imported.
