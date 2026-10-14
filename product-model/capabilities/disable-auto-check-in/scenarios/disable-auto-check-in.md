---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User turns off Enable Auto Check-In
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::working-location
  - text: The Product stops watching the area and turns auto check-in off for the working location
    kind: product
    actor: user
    entities:
      - entity: working-location
        effect: changes
        from: Auto check-in on
        to: Auto check-in off
        facts: []
    contexts:
      app:
        place: mobile-app::working-location
---

# Disable auto check-in

## Trigger

The User is on holiday or no longer wants automatic clocking.

## Outcome

No further check-ins or check-outs are recorded by location; the working location and its radius stay saved.

## Edge cases

- A position chosen while auto check-in was on takes effect once auto check-in is turned on again.
- If the phone refuses to stop watching, the Product says geofencing failed to stop and auto check-in stays on.
