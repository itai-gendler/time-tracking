---
id: time-tracking
summary: An offline phone app for recording working hours by hand, by NFC tag, by app-icon shortcut or automatically at a working location, with day, week and month balances against a daily target.
category: time-tracking
tags:
  - time-tracking
  - working-hours
  - mobile
  - offline
authors:
  - name: killi199
    url: https://github.com/killi199/time-tracking
license: Apache-2.0
languages:
  - en
  - de
limitations:
  - All data stays on the phone; nothing is uploaded or synchronized, and data moves between phones only through a CSV file the User exports and imports.
  - 'One person per installation: there are no accounts, sign-in, sharing or roles.'
  - Working time is recorded as check-in and check-out entries within one calendar day; a session never runs past midnight.
  - Automatic check-in follows one working location at a time, and the F-Droid (FOSS) build has no automatic check-in by location.
  - One daily work-hours target applies to every day that has entries; days without entries carry no target.
references:
  - kind: doc
    role: intent
    target: README.md
    title: README
  - kind: doc
    role: intent
    target: metadata/en-US/full_description.txt
    title: Store description
  - kind: doc
    role: context
    target: metadata/en-US/changelogs/242.txt
    title: Release notes
  - kind: code
    role: implementation
    target: src/db/database.ts#initDatabase
  - kind: code
    role: implementation
    target: app.config.ts
    title: Build configuration and FOSS switch
---

# Time Tracking

Time Tracking is an Android and iOS app in which one person records when their working day starts and ends and sees how their hours compare with a daily target. Each check-in and check-out is a time entry on a calendar day. The User records them with the Check In and Check Out button, with an NFC tag the app has written, with the quick action on the app icon, or automatically when the phone enters or leaves the working location. Entries can also be added, edited and deleted by hand. The Day, Week and Month views show the worked time, the balance against the daily work hours for that period, and an overall balance. Everything is kept on the phone, and the whole history can be exported to and imported from a CSV file. The app is available in English and German.

## Intent

The project promises to "keep track of your working hours with precision and ease", to "forget about manual clocking" by letting the phone clock in and out by location, NFC tag or home-screen shortcut, and that "your data belongs to you": the app "operates entirely offline", keeps its data "locally on your device" and is "never uploaded to any server", with CSV export and import so people can take their history with them.
