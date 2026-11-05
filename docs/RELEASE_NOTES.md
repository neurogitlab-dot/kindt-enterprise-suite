# Release Notes · v1.2.0-preview

**Kostenlose, proprietäre Ausgabe für nichtkommerzielle Nutzung. Kein Abonnement, kein Herstellerkonto, keine Online-Aktivierung. Kommerzielle Nutzung nur mit vorheriger Erlaubnis.**

## Produkt und Lieferumfang

Diese Preview präsentiert den vorhandenen Funktionsstand 1.2.0. Die ursprünglichen FINAL-Archive bleiben erhalten. Die zwei öffentlichen Linux-Downloads sind neue äußere Vertriebshüllen um die unveränderten geprüften Programme und ursprünglichen Drittbeilagen. Hinzu kommen die klar benannten Produktbedingungen der kostenlosen Edition; kein Anwendungsneubau, keine neue Funktion und keine Datenmigration wurden dafür vorgenommen.

| Plattform | Status |
| --- | --- |
| Linux x86-64 Desktop | Für öffentliche Bereitstellung vorbereitet, vollständiges `desktop-free.zip` |
| Linux x86-64 Server | Für öffentliche Bereitstellung vorbereitet, vollständiges `server-free.zip` |
| Windows x64 Desktop | Weitergabe noch gesperrt; kein öffentliches Release-Asset |
| Windows x64 Server | Weitergabe noch gesperrt; kein öffentliches Release-Asset |

Die öffentlichen Dateinamen sind `kindt-enterprise-suite-1.2.0-linux-x86_64-desktop-free.zip` und `kindt-enterprise-suite-1.2.0-linux-x86_64-server-free.zip`. Die im Release beigefügte `SHA256SUMS` bezieht sich auf diese vollständigen äußeren Pakete. Die inneren Originaldateien behalten ihre eigenen Prüfsummen.

## Funktionen der Version 1.2.0

- Dokumentarbeitsplatz mit Kategorien, Vorlagen, Textvorschau, Versionen, Vergleich und Archiv.
- Unternehmenskalender mit Tages-, Wochen- und Monatsansicht.
- Persönliche Benachrichtigungen, Gelesenstatus, Filter und Direktnavigation.
- Globale Unternehmenssuche mit Modul-/Typfiltern und serverseitiger Rechteprüfung.
- Persönliche Darstellung mit Vorlagen, Farbwählern und direkter HEX-Eingabe.
- Vorhandene FinanceForge-, PeopleForge-, OfficeForge-, AssetForge-, ServiceForge-, Executive- und Workflow-Funktionen bleiben erhalten.

## Betrieb und vorhandene Nachweise

Desktop mit SQLite, Server mit PostgreSQL-Anbindung und mehreren Browserclients. Der PostgreSQL-Server, passende Sicherungswerkzeuge und TLS-Zertifikate werden separat vorbereitet. Die Kernfunktionen arbeiten nach vorbereiteter Installation offline. Lokale Benutzerkonten bleiben als Zugriffsschutz erforderlich, ohne externe Registrierung.

Die vorhandenen Abnahmen werden wiederverwendet. Linux hatte einen vollständig grünen Lauf mit 294 Fällen einschließlich PostgreSQL 18.6/TLS; zusätzlich bestanden beide später neutral gebauten nativen Linux-Profile insgesamt 38 gezielte SQLite-/Offline-/HTTPS-/Neustartprüfungen. Diese Zahlen werden nicht zu einer künstlichen Gesamttestzahl addiert. Frühere GUI-, LAN-, Backup- und Rechtebeobachtungen behalten ihren dokumentierten Umfang. Für die neuen Vertriebshüllen wurden Transportintegrität, Lieferumfang, Bedingungen und öffentliche Unterlagen geprüft; keine neue vollständige Produktprüfung.

Linux ist auf Ubuntu 26.04.1 LTS x86-64/glibc 2.43 abgenommen. Andere Plattformbasen sind nicht durch diese Aussage abgedeckt. [Installation](INSTALLATION.md), [Upgrade](UPGRADE.md), [Prüfstand](CLEARANCE.md) und [Grenzen](LIMITATIONS.md).

## Lizenz

Die [Kindt Software Proprietary License v1.0](../LICENSE.txt) bleibt unverändert. Die [Produktbedingungen](../PRODUKTNUTZUNG_1_2.txt) bestimmen die erstmalige künftige Überlassung dieser kostenlosen Edition; bereits eingeräumte Rechte werden nicht rückwirkend verändert. Fremdlizenzen, Hinweise und vorgeschriebene Fremdquellen bleiben vollständig erhalten und werden dadurch nicht eingeschränkt. Keine vollständige Steuer-, Lohn-, DATEV- oder arbeitsrechtliche Konformität wird zugesagt.
