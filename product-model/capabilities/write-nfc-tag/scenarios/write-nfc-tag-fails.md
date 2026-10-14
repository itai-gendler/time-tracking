---
kind: edge
routes:
  app: Mobile app
steps:
  - text: The User taps Write Tag and holds a tag the phone cannot write to
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
  - text: The Product says the tag could not be written
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
---

# Fail to write an NFC tag

## Trigger

The tag is read-only, too small or moved away too early.

## Outcome

The tag is unchanged and the User can try again.
