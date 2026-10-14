---
kind: edge
routes:
  app: Mobile app
steps:
  - text: The User opens NFC Setup on a phone without NFC
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
  - text: The Product says NFC is not supported on this device and offers no writing
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app::nfc-setup
---

# Write an NFC tag on a phone without NFC

## Trigger

The phone has no NFC reader.

## Outcome

No tag can be written from this phone.
