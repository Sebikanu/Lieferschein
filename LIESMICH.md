# Lieferschein-App (Offline-Web-App / PWA)

## Dateien
- index.html – die komplette App (jsPDF und JSZip sind eingebettet, kein Internet nötig)
- manifest.json, sw.js, icon-192.png, icon-512.png – für Installation und Offline-Betrieb

## Installation auf Android
Kamera, Teilen-Funktion und Offline-Betrieb setzen voraus, dass die App über **HTTPS** ausgeliefert wird.
Das funktioniert NICHT, wenn du index.html einfach als Datei auf dem Handy öffnest.

Variante A – GitHub Pages (kostenlos):
1. Auf github.com ein neues Repository anlegen (kann privat sein, Pages für private Repos braucht aber ein kostenpflichtiges Konto; sonst öffentlich – die Daten selbst liegen ohnehin nur auf dem Handy, nicht im Repo).
2. Alle Dateien aus diesem Ordner hochladen.
3. Settings → Pages → Branch "main", Ordner "/ (root)" → Save.
4. Nach ca. 1 Minute die angezeigte URL in Chrome auf dem Handy öffnen.
5. Chrome-Menü (⋮) → "Zum Startbildschirm hinzufügen" / "App installieren".

Variante B – eigener Webserver (HTTPS) oder Firmen-Intranet: Ordnerinhalt ablegen, URL in Chrome öffnen, installieren.

Nach dem ersten Laden funktioniert die App komplett offline.

## Bedienung
- **+** legt einen neuen Lieferschein mit der nächsten Nummer an. Es wird automatisch gespeichert.
- **Fotos**: "Foto aufnehmen" öffnet die Kamera, "Aus Galerie" nimmt mehrere vorhandene Bilder. Fotos werden auf max. 1600 px verkleinert.
- **Unterschrift**: Name eintragen, mit dem Finger unterschreiben, "übernehmen".
- **PDF teilen / speichern**: öffnet das Android-Teilen-Menü (Mail, WhatsApp, Drive …).
- **ZIP**: PDF plus Original-Fotos des Lieferscheins.
- **Liste → Export**: CSV aller Lieferscheine (eine Zeile je Position, Semikolon, UTF-8 – öffnet direkt in Excel), ZIP aller Fotos, Backup.
- **Einstellungen**: Absender, Logo, Fußzeile, Nummernkreis (Präfix, Jahr, laufende Nr.), Einheitenliste.

## Wichtig: Datensicherung
Alle Daten liegen nur im Browser-Speicher dieses Handys. Sie gehen verloren, wenn
Chrome-Websitedaten gelöscht oder die App deinstalliert wird. Deshalb regelmäßig
**Backup sichern** (JSON-Datei inkl. Fotos). Mit **Backup laden** lassen sich die Daten auf einem
anderen Gerät wiederherstellen oder zusammenführen.

## Updates
Neue index.html auf den Server hochladen. Die App holt sich die neue Version beim nächsten
Start mit Internetverbindung, die Daten bleiben erhalten.
