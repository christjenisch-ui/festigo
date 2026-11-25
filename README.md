# FestiGo

FestiGo is a festival app for Brisa Fest 2027 (Marina Sur, València, 9–11 July).
It is a Progressive Web App (PWA): it runs in the phone's browser, can be added
to the home screen like a normal app, and keeps working without signal.

## Features

- **Home**: countdown to the festival, what's on stage now (during the festival),
  quick links to food, restrooms, water and first aid, your plan, and directions.
- **Map**: stages, food stalls, restrooms (queue times), free water, first aid and
  services. Tap a pin for details and a walking route. "Show my location" uses
  your phone's GPS and puts you on the map when you are inside the grounds.
  The download button saves the app on the phone for use with no signal.
- **Lineup**: three days, three stages. Star sets to build your plan; clashes are
  flagged and you get a reminder 15 minutes before a starred set.
- **Friends**: location sharing settings, meeting point, invite link (uses the
  phone's share sheet).
- **Momento**: once a day, at a surprise time between 09:00 and 21:00, everyone
  gets two minutes to post a photo. FestiGo opens the **phone's camera**, takes
  the back photo, then switches to the front camera for the selfie. Friends'
  posts stay blurred until you post yours.
- **Settings** (tap TÚ, top right): English / Español, Momento alerts, set
  reminders, offline map, add to home screen.

## Running it

The camera, GPS, notifications and offline mode only work when the app is served
over **https** (or from `localhost`). That is a browser security rule.

Quickest ways to put it online (free):

1. **Netlify Drop**: go to https://app.netlify.com/drop and drag this folder in.
2. **GitHub Pages**: push this folder to a repository, then Settings → Pages.

Open the https link on a phone. The first time Momento opens, the phone asks for
camera permission: tap Allow.

To try it on a computer: run `python3 -m http.server 8000` inside this folder and
open http://localhost:8000. Double-clicking index.html also opens the app, but
some browsers block the camera from a file, so it offers your camera app instead.

### Install on a phone
- Android (Chrome): Settings in FestiGo → "Add FestiGo to your home screen",
  or the browser menu → Install app.
- iPhone (Safari): Share → Add to Home Screen.

## Files

| File | What it is |
| --- | --- |
| index.html | The whole app (layout, styles, logic, both languages) |
| sw.js | Service worker: offline support and notifications |
| manifest.webmanifest | App name, colours and icons for installing |
| icon*.png / icon*.svg | App icons |

## Data

Your photos, plan, settings and meeting point are stored only on your device
(localStorage). The festival content (lineup, stalls, queue times) and the friend
group "Los de Malva-rosa" are built in. Sharing live location and Momento photos
between real users needs a backend server and user accounts, which this version
does not include.
