# Orca fork builds

Android builds of a personal Orca fork: the phone app (`com.stably.orca.mobile.dev`, "Orca Dev")
with its Wear OS companion. Only binaries live here; the source is private.

- **Phone:** install `orca-android-<build>.apk` from the [latest release](../../releases/latest).
  Later builds are offered inside the app (home card and Settings).
- **Watch:** nothing to do. The phone app carries the watch build of the same commit and sends it
  to the watch, which installs it. The first time, tap the notification on the watch and allow
  Orca to install apps. `orca-watch-<build>.apk` is the same build for a manual `adb install`.

`android/latest.json` is the manifest the app reads. A build number is the source commit's time in
minutes since 2026-01-01, so newer commits always have higher numbers.

The workflow in `.github/workflows/build-android.yml` checks the source branch every 30 minutes and
builds when it moved; it can also be started by hand.
