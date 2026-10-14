---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens Language Settings from Settings
    kind: actor
    actor: user
    entities:
      - entity: app-settings
        effect: reads
        facts:
          - Language
    contexts:
      app:
        place: mobile-app::language-settings
  - text: The User chooses English or German
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::language-settings
  - text: The Product keeps the chosen language and switches the app to it at once
    kind: product
    actor: user
    entities:
      - entity: app-settings
        effect: changes
        facts:
          - Language
    contexts:
      app:
        place: mobile-app::language-settings
---

# Choose English or German

## Trigger

The User wants the app in a language other than the phone's.

## Outcome

The app shows its text in the chosen language now and at every later start.
