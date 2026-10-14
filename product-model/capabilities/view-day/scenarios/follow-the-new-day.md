---
kind: edge
routes:
  app: Mobile app
steps:
  - text: The User returns to the app after midnight while the Day view showed the previous today
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::day
  - text: The Product moves the Day view to the new today and recalculates its figures
    kind: product
    actor: user
    entities:
      - entity: time-entry
        effect: reads
        facts:
          - Date
          - Time
          - Kind
      - entity: work-hours-entry
        effect: reads
        facts:
          - Daily work hours
    contexts:
      app:
        place: mobile-app::day
---

# Follow the new day after the app was in the background

## Trigger

The app was left open on today and the date changed while it was in the background.

## Outcome

The Day view shows the new today; a view the User had moved to another day stays where it was.

## Edge cases

- The Week and Month views do the same for the current week and month.
- When the phone's time zone changed while the app was in the background, the app restarts on return.
