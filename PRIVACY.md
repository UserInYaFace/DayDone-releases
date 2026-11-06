# Privacy

DayDone is a local family app. All processing is limited to the device.

## What data does the app process?

* Names, colors, avatars and profile photos of family members
* Tasks, subtasks, recurrence rules and completion states
* Star types, reward rules and the star/minute ledger
* Settings (for example selected calendars, assignments, auto-sync)
* Calendar events read through the Android calendar provider
* The central image library with default and imported images

## Where is the data stored?

* Family, task and star data is stored in a local SQLite database in the app's
  private storage.
* Profile photos are stored as JPEG files in the private app directory
  `member_photos`. Library and task images live under `images`. The database
  contains only file names; no photos are written to the Android gallery or
  uploaded.
* Settings are stored locally in Android DataStore. The per-app language is
  stored by AppCompat, also locally.
* Backups are created only on explicit action in the **More** tab and stay in
  the app's private storage. They contain the database, the profile photos and
  the image library. They are not encrypted and are not uploaded automatically.
* Android cloud backup is disabled (`android:allowBackup="false"`).

## Network and accounts

* The app requires no login and no account.
* The active calendar integration uses only the Android calendar provider.
  Synchronization with a Google account is handled by the device's system
  calendar, not by DayDone.
* There are no analytics, advertising or crash reporting SDKs.
* The direct Google Calendar API path is prepared in the code but has been
  disabled since version 1.5.0. While it is not configured, the app opens no
  network connections of its own.

## Permissions

* `READ_CALENDAR` / `WRITE_CALENDAR`: show calendars and create, edit or delete
  events. The permission is requested at runtime and can be revoked at any time
  in the Android settings. Without it, tasks, stars and family remain usable.
* `CAMERA`: only when taking a profile photo. The permission is requested at
  runtime and can be revoked at any time in the Android settings. Without it,
  selecting an image from the gallery remains possible.
* Gallery selection uses the Android Photo Picker or the document picker. This
  requires no storage permission; in particular, DayDone does not request
  access to the entire gallery.
* `INTERNET` / `ACCESS_NETWORK_STATE`: for the optional, currently inactive
  Google API path and the WorkManager network constraint.

## Sharing

No personal data is transmitted to the app developer or third parties.
Calendar data may be synchronized through the system calendar with the account
signed in there; the app has no influence over that.

## Deletion

Data can be removed in the Android settings via “Delete app data”. Individual
entries are deleted inside the app; ledger bookings are corrected rather than
deleted for traceability reasons.

## Contact

Bug reports and questions can be submitted through the issue tracker of this
repository.
