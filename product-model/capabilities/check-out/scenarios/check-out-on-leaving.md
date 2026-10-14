---
kind: edge
routes:
  app: Mobile app
steps:
  - text: The phone leaves the area around the working location while auto check-in is on
    kind: condition
    unattended: true
    entities:
      - entity: working-location
        effect: reads
        facts:
          - Position
          - Radius
    contexts:
      app:
        place: mobile-app
  - text: The Product finds an odd number of time entries for today
    kind: product
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
    contexts:
      app:
        place: mobile-app
  - text: The Product records a time entry for today at the current time with a note marking it as an automatic check-out
    kind: product
    entities:
      - entity: time-entry
        effect: creates
        facts:
          - Date
          - Time
          - Note
          - Late entry
    contexts:
      app:
        place: mobile-app
  - text: The Product posts a notification saying checked out at the time of the time entry
    kind: product
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Time
    contexts:
      app:
        place: mobile-app
---

# Check out automatically on leaving the working location

## Trigger

The phone reports that it leaves the working location's area, in the background, without the User opening the app.

## Outcome

Today has a new check-out at the moment the phone leaves the area and the User has been notified.

## Edge cases

- Leaving while already not working today records nothing and posts no notification.
- Only in the standard build; the F-Droid (FOSS) build never checks in or out by location.
