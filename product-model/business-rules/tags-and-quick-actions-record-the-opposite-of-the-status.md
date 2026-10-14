---
appliesTo:
  - type: capability-scenario
    id: check-in-with-nfc-tag
  - type: capability-scenario
    id: check-out-with-nfc-tag
  - type: capability-scenario
    id: check-in-with-quick-action
  - type: capability-scenario
    id: check-out-with-quick-action
references:
  - kind: code
    role: implementation
    target: src/services/NFCService.ts#initNfcService
  - kind: code
    role: implementation
    target: src/services/QuickActionService.ts#initQuickActions
---

# A tag tap or quick action records the opposite of today's working status

The same tag and the same quick action check the User in while today has an even number of entries and out while it has an odd number; the User does not choose which.
