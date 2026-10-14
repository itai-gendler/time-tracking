---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User chooses Automatic (System) in Language Settings
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::language-settings
  - text: The Product keeps Automatic and switches the app to German when the phone's language is German and to English otherwise
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

# Follow the phone's language

## Trigger

The User wants the app to match the phone again.

## Outcome

The app follows the phone's language, read again at every start.
