---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens Working Location from the menu
    kind: actor
    actor: user
    entities:
      - entity: working-location
        effect: reads
        facts:
          - Position
          - Radius
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product centres the map on the saved working location, or on the phone's current position when none is set yet
    kind: product
    actor: user
    entities:
      - entity: working-location
        effect: reads
        facts:
          - Position
    contexts:
      app:
        place: mobile-app::working-location
  - text: The User long-presses the place of work on the map while auto check-in is off
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product marks the position with the radius drawn around it and keeps both for the working location
    kind: product
    actor: user
    entities:
      - entity: working-location
        effect: changes
        facts:
          - Position
          - Radius
    contexts:
      app:
        place: mobile-app::working-location
---

# Set the working location

## Trigger

The User wants the app to know where they work.

## Outcome

The working location is saved with its radius and ready for auto check-in.

## Edge cases

- While no position is set, the page asks the User to long-press the map.
