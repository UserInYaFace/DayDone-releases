# DayDone – Releases

DayDone ist eine lokale Familien-App für Aufgaben, Sterne und Kalender.
Dieses Repository stellt ausschließlich die veröffentlichten
Release-Artefakte bereit: die installierbare Android-APK und die zugehörigen
SHA-256-Prüfsummen. Der Quellcode ist privat und wird hier nicht veröffentlicht.

## Download

Die aktuelle Version steht unter
[Releases](https://github.com/UserInYaFace/DayDone-releases/releases/latest).

| Datei | Zweck |
|---|---|
| `DayDone-<version>.apk` | Installierbare Android-App (ab Android 8.0 / API 26) |
| `SHA256SUMS` | SHA-256-Prüfsummen der veröffentlichten Dateien |

## Installation

1. Die APK aus dem neuesten Release herunterladen.
2. Auf dem Android-Gerät die Installation aus unbekannten Quellen für den
   verwendeten Browser bzw. Dateimanager erlauben.
3. Die APK öffnen und installieren.
4. Die Freigabe nach der Installation wieder entziehen.

DayDone wird mit einem eigenen Schlüssel signiert. Updates müssen deshalb
immer aus diesem Repository stammen; eine APK aus einer anderen Quelle lässt
sich nicht als Update installieren.

## Prüfsumme

```bash
sha256sum -c SHA256SUMS
```

## Datenschutz

DayDone verarbeitet alle Daten lokal auf dem Gerät. Details stehen in
[PRIVACY.md](PRIVACY.md).

## Quellcode

Der Quellcode wird bewusst nicht veröffentlicht. Fehlerberichte und Fragen
können über den Issue-Tracker dieses Repositories eingereicht werden.
