---
singleton: true
domain: working-location
references:
  - kind: code
    role: implementation
    target: src/screens/menu/GeofenceSetupScreen.tsx#GeofenceSetupScreen
  - kind: code
    role: implementation
    target: src/services/LocationTask.ts#LOCATION_TASK_NAME
---

# Working location

The one place whose surroundings check the User in and out automatically. It exists only in the standard build; the F-Droid (FOSS) build has no working location.

## Information kept

- **Position** — the point on the map the User chose
- **Radius** — how far around the position counts as being at work, from 100 to 1000 meters in steps of 50; 100 meters until changed

## States

### Auto check-in off

Nothing is watched; position and radius can be changed freely.

### Auto check-in on

The Product watches, in the background, for the phone entering and leaving the area around the position and records check-ins and check-outs.
