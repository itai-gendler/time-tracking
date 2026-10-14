---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User turns on Enable Auto Check-In on Working Location
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
  - text: The Product asks the phone for permission to use the location in the background
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The User allows background location
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product starts watching the area around the working location and turns auto check-in on
    kind: product
    actor: user
    entities:
      - entity: working-location
        effect: changes
        from: Auto check-in off
        to: Auto check-in on
        facts: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product confirms that geofencing is enabled
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
---

# Enable auto check-in

## Trigger

The User wants to stop clocking by hand.

## Outcome

From now on the User is checked in on arriving at and checked out on leaving the working location, with a notification each time.

## Edge cases

- If the phone refuses to start watching the area, the Product says geofencing failed to start and auto check-in stays off.
