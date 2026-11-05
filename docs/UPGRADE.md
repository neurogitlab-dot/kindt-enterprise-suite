# Upgrade auf 1.2.0 und Rückfall

Das Label `v1.2.0-preview` ändert weder Programmversion noch Datenformat. Die vorbereiteten Pakete enthalten das unveränderte Programm 1.2.0 FINAL. Die vollständigen Linux-Vertriebshüllen sind für die öffentliche Auswahl vorbereitet; Windows bleibt vom öffentlichen Upload ausgeschlossen. Die neuen Produktbedingungen gelten für die erstmalige künftige Überlassung dieser kostenlosen Ausgabe, nicht rückwirkend für bereits eingeräumte Rechte. [Lieferumfang](DISTRIBUTION.md).

## Vorbereiten

1. Alle Benutzer abmelden und den bisherigen Anwendungsprozess geordnet beenden.
2. Eine vollständige Sicherung erstellen. Zusätzlich alten Programmordner, gesamte Datenablage einschließlich Dokumentdateien und bestehende Konfiguration getrennt erhalten. Eine einzelne kopierte SQLite-Datei genügt nicht.
3. Die Wiederherstellung zunächst mit einer isolierten Kopie prüfen. Bei PostgreSQL einen getrennten Zielbereich mit leerem Schema und leerem Dokumentverzeichnis verwenden.
4. Das passende neue Archiv vollständig in einen neuen Programmordner entpacken und die SHA-256-Prüfsumme vergleichen. Keine einzelnen Laufzeitbibliotheken zwischen Programmordnern austauschen.

## Daten übernehmen

Den neuen nativen Starter mit dem ausdrücklich gewählten geschützten Datenverzeichnis starten:

```text
KindtEnterpriseSuite.exe --data-dir "<geschützter-Datenordner>"
KindtEnterpriseSuiteServer.exe --data-dir "<geschützter-Datenordner>"
./KindtEnterpriseSuite/KindtEnterpriseSuite --data-dir "<geschützter-Datenordner>"
./KindtEnterpriseSuiteServer/KindtEnterpriseSuiteServer --data-dir "<geschützter-Datenordner>"
```

Nur die zum gewählten Paket passende Zeile verwenden. Vorhandene PostgreSQL- und TLS-Konfiguration übernehmen und die Verbindung beziehungsweise Zertifikatskette prüfen. Ein Suite-Prozess je Datenverzeichnis oder Schema bleibt der vorgesehene Betriebsmodus.

1.2.0 verwendet die vorhandenen versionierten Ressourcen. Es gibt keine destruktive Schemaumwandlung oder pauschale Umschreibung alter Geschäftsdaten. Benutzer, Rollen, Mandanten, Freigaben und frühere Dateiversionen werden erhalten. Alte Dokumente ohne Sichtbarkeitsfeld bleiben gemeinsam sichtbar; neue private Inhalte folgen den Eigentümer- und Administrationsrechten. Neue Kalenderzeitpunkte benötigen explizite Zeitzonen.

Nach der Übernahme Anmeldung, Fachdatensätze, Dokumentversionen und Berechtigungen kontrollieren. Persönliche Einstellungen speichern, neu anmelden und den erhaltenen Stand prüfen. Kalender, Suche und Benachrichtigungen mit passend berechtigten Benutzerkonten kontrollieren. Anschließend eine neue vollständige Sicherung erstellen.

## Zu einem früheren Datenstand zurückkehren

Der Rückfall verwendet **die alte Programmversion zusammen mit dem vollständigen, vor dem Upgrade gesicherten Datenstand**.

1. Neue Anwendung beenden und den aktuellen Stand zusätzlich sichern.
2. Den vorherigen Datenstand in eine neue isolierte Datenablage wiederherstellen. Bei PostgreSQL den dokumentierten nativen Wiederherstellungspfad in ein separates leeres Zielschema verwenden.
3. Die alte Programmversion mit diesem wiederhergestellten Stand starten und Anmeldung, Rollen, Dokumentversionen und Fachdatensätze kontrollieren.
4. Erst nach der eigenen erfolgreichen Betriebsprüfung den früheren Stand übernehmen.

Änderungen nach dem Sicherungszeitpunkt sind im Rückfallstand nicht enthalten. Ein verlustfreier In-Place-Downgrade produktiv veränderter 1.2.0-Daten wird nicht zugesagt. Alte und neue Programme dürfen nicht gleichzeitig auf denselben Datenordner oder dasselbe Schema schreiben.

## Vorhandener Nachweis

Die bestehende Abnahme umfasst native Starts von 1.1.0 und 1.2.0 sowie Rückkehr zur alten Version mit dem wiederhergestellten früheren Datenstand. Für PostgreSQL wurde geprüft, dass nachträgliche Änderungen einschließlich einer zusätzlichen Dokumentversion im Rückfallstand fehlen. Diese Preview-Vorbereitung führt keine neuen Upgradeprüfungen aus und ersetzt keine Wiederherstellungsprüfung mit der eigenen Betriebsumgebung.