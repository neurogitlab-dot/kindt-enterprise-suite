# Lokale GitHub-Veröffentlichungsmappe · Kindt Enterprise Suite 1.2.0

**Vorbereitet, nicht veröffentlicht. Linux öffentlich vorbereitbar; Windows gesperrt und von öffentlichen Uploads ausgeschlossen. Die Veröffentlichung benötigt weiterhin die ausdrückliche Betreiberfreigabe.**

- `repository/`: ausschließlich kuratierte öffentliche README, Dokumentation, Lizenz-/Produktbedingungen und fünf unveränderte echte Anwendungsbilder. Eigene Anwendungssourcen sind nicht enthalten.
- `release-assets/`: ausschließlich zwei vollständige Linux-Vertriebshüllen, öffentliche SHA-256 und lokale Upload-Allowlist. Jede Hülle enthält unveränderte geprüfte Anwendung und ursprüngliche vollständige Lizenz-/Quellenbeilagen sowie die neuen Produktbedingungen der kostenlosen Edition.
- `RELEASE_DESCRIPTION.md`: vorbereitete deutsche GitHub-Releasebeschreibung.
- `operator/`: **nicht öffentlich hochladen**. Manuelle Uploadanleitung, Windows-Übergabe, persönliche Restschritte und Prüfnachweise; keine fingierten Annahmen.
- `PACKAGE_STATUS.json`: Status und Zuordnung aller vier Plattformprofile.
- `VERIFICATION.json` und `SHA256SUMS`: tatsächliche lokale Lieferkontrolle und Prüfsummen dieser Gesamtmappe. Die öffentliche SHA-Liste liegt separat unter `release-assets/`.

Die kanonische Kindt Software Proprietary License v1.0 bleibt unverändert. Die ausdrücklich beauftragte Produktregel bestimmt die kostenlose **nichtkommerzielle** Nutzung dieser erstmaligen künftigen Überlassung; kommerzielle Nutzung durch Dritte benötigt Erlaubnis. Bestehende tatsächlich eingeräumte Rechte werden nicht rückwirkend geändert. Fremdlizenzen und vorgeschriebene Fremdquellen bleiben vollständig erhalten.

Die ursprünglichen FINAL-Archive und die bisherige r3-Mappe bleiben erhalten. Es wurde kein Anwendungsneubau durchgeführt. Die neue äußere Linux-Paketierung dient der vollständigen, selbsttragenden Mitlieferung der Bedingungen und Beilagen; die Innenarchive bleiben bytegleich und besitzen weiterhin ihre alten Prüfsummen.

Beginnen mit [manueller Uploadanleitung](operator/MANUELLER_GITHUB_UPLOAD.md), [persönlichen Restschritten](operator/PERSOENLICHE_RESTSCHRITTE.md) und [Paketstatus](PACKAGE_STATUS.json). Nicht die gesamte Mappe, den Entwicklungsprojektordner oder vorhandene FINAL-/VM-/Buildarchive hochladen.
