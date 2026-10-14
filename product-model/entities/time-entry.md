---
references:
  - kind: code
    role: implementation
    target: src/db/database.ts#addEvent
  - kind: code
    role: implementation
    target: src/types.d.ts#TimeEvent
  - kind: code
    role: implementation
    target: src/components/EventListItem.tsx#EventListItem
---

# Time entry

One recorded check-in or check-out moment on a calendar day. The app calls them entries when adding or editing them ("Add Entry") and events when deleting them ("Delete Event"), and lists each one as "Check In at 08:00" or "Check Out at 17:00".

## Information kept

- **Date** — the calendar day the entry belongs to, never after today
- **Time** — the hour and minute of the entry in the phone's local time
- **Note** — optional free text; entries recorded by NFC tag, quick action or working location carry a note saying how they were recorded
- **Late entry** — whether the entry was added after the fact, shown as "(Late Entry)" beside its time
- **Kind** — check-in or check-out, read from the entry's place among the day's entries in time order: the first, third and every other odd entry is a check-in, the others are check-outs
