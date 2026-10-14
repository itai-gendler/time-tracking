---
kind: edge
routes:
  app: Mobile app
steps:
  - text: The User turns on Enable Auto Check-In for a working location
    kind: actor
    actor: user
    entities:
      - entity: working-location
        effect: reads
        facts:
          - Position
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
  - text: The User does not allow background location
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product says background location permission is required and leaves auto check-in off
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
---

# Refuse auto check-in without background location

## Trigger

The phone's permission prompt is answered with anything but always allowing the location.

## Outcome

Auto check-in stays off; it can be turned on once the permission is given in the phone's settings.
