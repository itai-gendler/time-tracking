---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens Settings and taps Daily work hours
    kind: actor
    actor: user
    entities:
      - entity: work-hours-entry
        effect: reads
        facts:
          - Daily work hours
    contexts:
      app:
        place: mobile-app::settings
  - text: The User picks hours and minutes and confirms
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::settings
  - text: The Product records a work hours entry effective today with the chosen daily work hours
    kind: product
    actor: user
    entities:
      - entity: work-hours-entry
        effect: creates
        facts:
          - Effective date
          - Daily work hours
    contexts:
      app:
        place: mobile-app::settings
  - text: The Product says that changes apply from today onward and earlier days keep their previous target
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::settings
---

# Change the daily work hours

## Trigger

The User's contract changes, for example to part-time.

## Outcome

Settings shows the new daily work hours; balances from today on use it and earlier balances are unchanged.
