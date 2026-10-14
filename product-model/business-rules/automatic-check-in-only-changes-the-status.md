---
appliesTo:
  - type: capability-scenario
    id: check-in-on-arrival
  - type: capability-scenario
    id: check-out-on-leaving
references:
  - kind: code
    role: implementation
    target: src/services/LocationTask.ts#LOCATION_TASK_NAME
---

# Arriving or leaving records an entry only when it changes the working status

Entering the working location checks the User in only while today's entries leave them not working, and leaving checks them out only while they are working; otherwise nothing is recorded and no notification is posted.
