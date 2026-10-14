---
kind: primary
routes:
  app: Mobile app
steps:
  - text: The User opens NFC Setup from the menu and taps Write Tag
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
  - text: The Product waits for a tag, showing Ready to scan
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
  - text: The User holds a writable NFC tag to the phone
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
  - text: The Product writes the app's check-in link onto the tag and says the tag was written
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
---

# Write an NFC tag

## Trigger

The User places a tag at the office door or desk.

## Outcome

The tag checks the User in or out whenever the phone is held to it.

## Edge cases

- Cancel stops waiting for a tag without a message.
