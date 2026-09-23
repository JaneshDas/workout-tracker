# Workout Tracker

A single-page site to track daily plank hold times, with a calendar to browse history.

- Open the page: today's date is checked against Firestore. If there's no entry yet, you can enter how long you held your plank. Once saved, it's locked in for the day.
- Use the calendar below to click any date and see the plank time logged for it.

## Stack

- Plain HTML/CSS/JS, no build step (`index.html`).
- Firebase (Firestore) for storage, with anonymous auth so each visitor gets their own private data without a login screen. Data is scoped per anonymous user (tied to the browser) — it doesn't carry over to a different browser or device, and isn't shared with anyone else.

## Deployment

Hosted via GitHub Pages: Settings → Pages → source = this branch, root folder.

## Firestore rules

`firestore.rules` restricts reads/writes to authenticated (including anonymous) users. Deploy with:

```
firebase deploy --only firestore:rules --project workout-tracker-janesh
```
