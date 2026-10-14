---
appliesTo:
  - type: entity
    id: time-entry
    facts:
      - Kind
references:
  - kind: code
    role: implementation
    target: src/screens/DayView.tsx#DayView
  - kind: code
    role: implementation
    target: src/services/NFCService.ts#initNfcService
---

# A day's entries alternate check-in and check-out in time order

The first entry of a day in time order is a check-in, the next a check-out, and so on. Whether an entry is a check-in or a check-out is not kept with it: adding, moving or deleting an entry switches every later entry of that day. A day with an odd number of entries has an open session, and on today the status then reads Currently Working.
