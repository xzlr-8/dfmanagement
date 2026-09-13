# DFManagement

A macOS admin/MDM-style panel built in Swift for managing loaner devices at Disruptive Force's GoSHackathon events.

## What it does

- **Remote lock/unlock** of managed devices
- **PIN management** for device access control
- **Chrome tab monitoring** to keep an eye on what loaner machines are being used for
- **Cloudflare R2 as the backend store** — device state is kept in a `devices.json` object, written/read using AWS Signature V4 signing (R2 is S3-compatible)

There's also a companion kiosk-mode screen (separate Python/tkinter app, not included in this repo) that shows a fullscreen, focus-locked loan agreement for anyone borrowing hardware — built for GoSHackathon at Mandurah CoderDojo.

## Repo contents

This repo currently ships as a compiled disk image (`DFManagement.dmg`) rather than raw source — grab it and mount it on macOS to install/run the app.

## Background

Development involved working through some gnarly Swift actor/retry-loop crashes and R2 sync edge cases to get device state syncing reliably across the panel and the devices it manages.

## Status

Built for and used at GoSHackathon; treat as event-specific tooling rather than a general-purpose MDM.
