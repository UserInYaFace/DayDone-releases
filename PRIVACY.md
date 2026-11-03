# Datenschutz

DayDone ist eine lokale Familien-App. Die Verarbeitung ist auf das Gerät
beschränkt.

## Welche Daten verarbeitet die App?

* Namen, Farben, Avatare und Profilfotos der Familienmitglieder
* Aufgaben, Teilaufgaben, Wiederholungen und Abschlussstände
* Sternarten, Belohnungsregeln und das Stern-/Minuten-Ledger
* Einstellungen (z. B. ausgewählte Kalender, Zuordnungen, Auto-Sync)
* Kalendertermine, die über den Android-Kalender-Provider gelesen werden
* die zentrale Bildbibliothek mit Standard- und importierten Bildern

## Wo liegen die Daten?

* Familien-, Aufgaben- und Sterndaten liegen in einer lokalen SQLite-Datenbank
  im privaten App-Speicher.
* Profilfotos werden als JPEG-Dateien im privaten App-Verzeichnis
  `member_photos` gespeichert. Bibliotheks- und Aufgabenbilder liegen unter
  `images`. Die Datenbank enthält nur Dateinamen; es werden keine Fotos in die
  Android-Galerie geschrieben oder hochgeladen.
* Einstellungen liegen lokal in Android DataStore.
* Backups werden nur auf ausdrückliche Aktion im „Mehr“-Tab im privaten
  App-Speicher erzeugt. Sie enthalten die Datenbank, die Profilfotos und die
  Bildbibliothek. Sie sind nicht verschlüsselt und werden nicht automatisch
  hochgeladen.
* Android Cloud-Backup ist deaktiviert (`android:allowBackup="false"`).

## Netzwerk und Konten

* Die App verlangt keine Anmeldung und kein Konto.
* Die aktive Kalenderanbindung nutzt ausschließlich den
  Android-Kalender-Provider. Die Synchronisierung mit einem Google-Konto
  übernimmt der System-Kalender des Geräts, nicht DayDone.
* Es gibt keine Analyse-, Werbe- oder Crash-Reporting-SDKs.
* Der direkte Google-Calendar-API-Pfad ist im Code vorbereitet, seit Version
  1.5.0 aber deaktiviert. Solange er nicht konfiguriert ist, baut die App
  keine eigenen Netzwerkverbindungen auf.

## Berechtigungen

* `READ_CALENDAR` / `WRITE_CALENDAR`: Kalender anzeigen und Termine anlegen,
  bearbeiten oder löschen. Die Berechtigung wird zur Laufzeit erfragt und kann
  jederzeit in den Android-Einstellungen entzogen werden. Ohne sie bleiben
  Aufgaben, Sterne und Familie nutzbar.
* `CAMERA`: nur beim Aufnehmen eines Profilfotos. Die Berechtigung wird zur
  Laufzeit erfragt und kann jederzeit in den Android-Einstellungen entzogen
  werden. Ohne sie bleibt die Auswahl aus der Galerie möglich.
* Die Galerie-Auswahl nutzt den Android Photo Picker bzw. den
  Dokumenten-Picker. Dafür ist keine Speicherberechtigung erforderlich;
  DayDone fordert insbesondere keinen Zugriff auf die gesamte Galerie an.
* `INTERNET` / `ACCESS_NETWORK_STATE`: für den optionalen, derzeit inaktiven
  Google-API-Pfad und die WorkManager-Netzwerkbedingung.

## Weitergabe

Es werden keine personenbezogenen Daten an den App-Hersteller oder Dritte
übermittelt. Kalenderdaten können über den System-Kalender mit dem dort
angemeldeten Konto synchronisiert werden; darauf hat die App keinen Einfluss.

## Löschung

Die Daten lassen sich in den Android-Einstellungen über „App-Daten löschen“
entfernen. Einzelne Einträge werden in der App gelöscht; Ledger-Buchungen
werden aus Nachvollziehbarkeitsgründen korrigiert statt gelöscht.

## Kontakt

Fehlerberichte und Fragen können über den Issue-Tracker dieses Repositories
eingereicht werden.
