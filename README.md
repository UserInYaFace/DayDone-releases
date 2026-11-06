# DayDone – Releases

DayDone is a local family app for tasks, stars and calendars. This repository
only provides the published release artifacts: the installable Android APK and
its SHA-256 checksums. The source code is private and is not published here.

## Download

The current version is available under
[Releases](https://github.com/UserInYaFace/DayDone-releases/releases/latest).

| File | Purpose |
|---|---|
| `DayDone-<version>.apk` | Installable Android app (Android 8.0 / API 26 and newer) |
| `SHA256SUMS` | SHA-256 checksums of the published files |

## Installation

1. Download the APK from the latest release.
2. On the Android device, allow installation from unknown sources for the
   browser or file manager you use.
3. Open the APK and install it.
4. Revoke the permission again after installation.

DayDone is signed with its own key. Updates must therefore always come from
this repository; an APK from another source cannot be installed as an update.

## Checksum

```bash
sha256sum -c SHA256SUMS
```

## Language

The app speaks English and German. By default it follows the system language;
the language can be changed per app under **More → Language**. English is the
fallback when the system language is not available.

## Privacy

DayDone processes all data locally on the device. Details are in
[PRIVACY.md](PRIVACY.md).

## Source code

The source code is deliberately not published. Bug reports and questions can be
submitted through the issue tracker of this repository.
