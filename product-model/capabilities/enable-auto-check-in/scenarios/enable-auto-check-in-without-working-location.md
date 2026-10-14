---
kind: validation
routes:
  app: Mobile app
steps:
  - text: The working location has no position yet
    kind: condition
    entities:
      - entity: working-location
        effect: reads
        facts:
          - Position
    contexts:
      app:
        place: mobile-app::working-location
  - text: The User turns on Enable Auto Check-In
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product asks the User to long-press the map to set the work location and leaves auto check-in off
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
---

# Refuse auto check-in without a working location

## Trigger

The User turns the switch on before choosing a place.

## Outcome

Auto check-in stays off until a position is set.
