---
kind: edge
routes:
  app: Mobile app
steps:
  - text: The User chooses Export CSV on a phone without a share sheet
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
  - text: The Product says sharing is not available on this device
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: mobile-app
---

# Export CSV on a phone that cannot share

## Trigger

The phone offers no way to share files.

## Outcome

No file is handed over.
