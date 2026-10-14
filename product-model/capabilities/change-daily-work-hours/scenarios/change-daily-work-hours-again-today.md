---
kind: edge
routes:
  app: Mobile app
steps:
  - text: Today already has a work hours entry
    kind: condition
    entities:
      - entity: work-hours-entry
        effect: reads
        facts:
          - Effective date
    contexts:
      app:
        place: mobile-app::settings
  - text: The User picks other hours and minutes for Daily work hours and confirms
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::settings
  - text: The Product replaces the daily work hours of today's work hours entry
    kind: product
    actor: user
    entities:
      - entity: work-hours-entry
        effect: changes
        facts:
          - Daily work hours
    contexts:
      app:
        place: mobile-app::settings
---

# Change the daily work hours twice on one day

## Trigger

The User corrects a value set earlier the same day.

## Outcome

Only the latest value applies from today; no second entry for today is kept.
