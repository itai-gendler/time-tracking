---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The working location has a position and auto check-in is off
    kind: condition
    entities:
      - entity: working-location
        effect: reads
        facts:
          - Position
    contexts:
      app:
        place: mobile-app::working-location
  - text: The User moves the radius slider between 100 and 1000 meters
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product redraws the area and keeps the new radius for the working location
    kind: product
    actor: user
    entities:
      - entity: working-location
        effect: changes
        facts:
          - Radius
    contexts:
      app:
        place: mobile-app::working-location
---

# Change the radius of the working location

## Trigger

The check-ins come too early or too late because the area is too large or too small.

## Outcome

The working location keeps the new radius.
