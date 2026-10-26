# Beacon

**When disaster strikes, the deadliest thing isn't the disaster — it's not knowing where to go.**

Beacon is a disaster-safety and coordination app that keeps people and first responders connected when an emergency hits. It turns any phone into a lifeline: a live map of who's safe and who needs help, guided routes to the nearest clear exit, and a dedicated mode for first responders to triage and track rescues.

## The problem

In disaster after disaster — from the 1903 Iroquois Theatre fire (602 dead, most crushed at blocked exits) to the 2021 Astroworld tragedy (10 killed in a crowd no one could map) — most people don't die from the fire or the collapse. They die from the chaos of not knowing where it's safe to go. I was inspired by crises like the earthquakes and unrest in Venezuela, where people had phones in their pockets but no coordinated way to find each other. Beacon exists to close that gap.

## Features

- **Safety dashboard** — a color-coded risk scale (green → red) with one-tap "I'm safe" and "I need help."
- **Live map** — see the people around you, color-coded by status (safe, no response, needs help), with an animated path guiding you to the nearest clear exit.
- **Building floor plans** — load a building by address and mark its exits as clear or blocked so everyone knows the way out.
- **People** — find loved ones, see their status, get directions, and call them directly.
- **SOS** — reach 911 and emergency contacts fast.
- **First-responder mode** — switches the app into an incident-command view with a live triage board to mark who's rescued, who's urgent, and who hasn't been found yet.
- **Recover** — breathing and grounding exercises for after the event.
- **Dark mode** and persistent onboarding.

## Tech stack

- **Frontend:** React Native (Expo), React Navigation
- **Backend:** Node.js, Express, Socket.IO (real-time presence)
- **Maps:** react-native-maps
- **Storage:** AsyncStorage for local persistence

## Running it

1. Install dependencies: `npm install`
2. Start the backend: `cd server && npm install && node server.js`
3. Start the app: `npx expo start --dev-client`
4. Open on an iOS device or simulator.

## Limitations & future work

- **Live alerts** currently use a simulated trigger; a production version would integrate official feeds like USGS ShakeAlert and Wireless Emergency Alerts.
- **Indoor positioning** is hard without installed hardware (BLE beacons), so Beacon uses crowd-sourced floor plans and coarse GPS.
- **Network dependence:** the live map needs connectivity. A key next step is running the server on a local edge device (such as a Raspberry Pi) so Beacon keeps working when internet infrastructure goes down.

## Author

Built by Amrit Sai Arasamangalam for the 2026 Congressional App Challenge.
