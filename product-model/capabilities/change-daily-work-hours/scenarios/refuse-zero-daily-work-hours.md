---
kind: validation
routes:
  app: Mobile app
steps:
  - text: The User picks 0 hours and 0 minutes for Daily work hours and confirms
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::settings
  - text: The Product says the daily work hours must be greater than 0 and keeps the previous target
    kind: product
    actor: user
    entities:
      - entity: work-hours-entry
        effect: reads
        facts:
          - Daily work hours
    contexts:
      app:
        place: mobile-app::settings
---

# Refuse zero daily work hours

## Trigger

The User sets the target to nothing, for example for a free day.

## Outcome

Nothing is recorded and the previous daily work hours stay in effect.
