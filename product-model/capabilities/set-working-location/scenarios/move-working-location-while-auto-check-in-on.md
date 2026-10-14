---
kind: edge
routes:
  app: Mobile app
steps:
  - text: Auto check-in is on for the working location
    kind: condition
    entities:
      - entity: working-location
        effect: reads
        facts: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The User long-presses a new place on the map
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product marks the new place and says to turn auto check-in off and on again to apply it
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
---

# Move the working location while auto check-in is on

## Trigger

The User has moved office while auto check-in is running.

## Outcome

Check-ins and check-outs still follow the previous area until auto check-in is turned off and on again.

## Edge cases

- Moving the radius slider while auto check-in is on is not applied either until auto check-in is turned off and on again.
