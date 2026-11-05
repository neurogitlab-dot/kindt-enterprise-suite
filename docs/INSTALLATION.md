# Installation und Betrieb

Die öffentliche Auswahl enthält zwei vollständige Linux-Vertriebshüllen. Windows ist nicht Teil der öffentlichen Downloads; die folgenden vorhandenen Windows-Betriebshinweise gelten erst für eine tatsächlich rechtmäßig individuell überlassene Ausgabe. Kostenlos ist die nichtkommerzielle Nutzung, kommerzielle Nutzung benötigt Erlaubnis. [Produktbedingungen](../PRODUKTNUTZUNG_1_2.txt), [Lieferumfang](DISTRIBUTION.md).

Kein Herstellerkonto, keine Online-Aktivierung und kein Abonnement. Die lokale Einrichtung eines Administratorkontos und die Benutzeranmeldung bleiben als Zugriffsschutz erforderlich. Kernfunktionen funktionieren nach vorbereiteter Installation vollständig offline.

## Passendes Paket auswählen

Windows benötigt Windows 10 oder neuer mit x64. Die Linux-Abnahme erfolgte auf Ubuntu 26.04.1 LTS x86-64 mit glibc 2.43; daraus folgt keine Zusage für andere Distributionen oder ältere glibc-Versionen. Ein lokal vorhandener Browser ist erforderlich. Python und Node müssen auf dem portablen Zielgerät nicht gesondert installiert werden.

Das Desktoppaket verwendet SQLite. Das getrennte Serverpaket enthält die PostgreSQL-Anbindung. PostgreSQL-Server und passende `pg_dump`-/`pg_restore`-Werkzeuge gehören nicht zum Lieferumfang. Vollständig geprüft wurde PostgreSQL 18.6; für das dokumentierte PostgreSQL-18-Profil werden Server und stabile, zueinander passende Werkzeuge mindestens 18.6 vorausgesetzt.

## Vollständige kostenlose Ausgabe entpacken

Zuerst SHA-256 der äußeren `*-free.zip` prüfen und diese mit dem vorhandenen Archivmanager vollständig entpacken. `START_HIER.txt`, die unveränderte `LICENSE.txt` und `PRODUKTNUTZUNG_1_2.txt` lesen. Dann das unveränderte innere Anwendungsarchiv unter `application/` entpacken. Die Produktbedingungen der kostenlosen Ausgabe dauerhaft neben dem entpackten Programm erhalten; die ursprünglichen Lizenz-/Quellenbeilagen unter `notices-and-sources/` vollständig behalten. Das alte Innenarchiv allein ist nicht der vollständige Download dieser Ausgabe. Bereits früher eingeräumte Rechte werden nicht rückwirkend geändert.

## Entpacken und lokal starten

1. SHA-256 des vollständigen Archivs mit der zugehörigen Prüfsumme vergleichen und alle Lizenzbeilagen lesen.
2. Das gesamte Archiv in einen neuen Programmordner entpacken. Unterverzeichnisse wie `_internal` und mitgelieferte Drittanbieterkomponenten vollständig erhalten.
3. Ein eigenes geschütztes Datenverzeichnis festlegen. Programmdateien und Geschäftsdaten getrennt halten; nur berechtigte Konten erhalten Dateisystemzugriff.
4. Den passenden nativen Starter mit dem gewählten Datenpfad starten. Die folgenden Platzhalter durch eigene Pfade ersetzen.

Windows, im entpackten Programmordner:

```text
KindtEnterpriseSuite.exe --data-dir "<geschützter-Datenordner>"
```

Linux, im Verzeichnis neben dem entpackten Anwendungsordner:

```text
./KindtEnterpriseSuite/KindtEnterpriseSuite --data-dir "<geschützter-Datenordner>"
```

Der Starter verwendet den vorhandenen lokalen Browser. Der lokale Einzelplatzbetrieb bindet an die Loopback-Adresse. Beim ersten Start den im Datenverzeichnis erzeugten Einrichtungsschlüssel aus `setup-token.txt` verwenden und ein individuelles Administratorkonto einrichten. Es gibt kein Standardpasswort und keine automatisch eingespielten Beispieldaten. Einrichtungsschlüssel und Kennwörter vertraulich behandeln.

## Server und HTTPS im LAN

Ein Suite-Prozess mit mehreren Browserclients ist der geprüfte Betriebsmodus. Keine gemeinsam geöffnete SQLite-Datei auf einer Netzwerkfreigabe verwenden. Für den PostgreSQL-Betrieb das Serverpaket und ein eingeschränktes Datenbankkonto in einer dedizierten Datenbank verwenden.

Die vorhandenen Konfigurationsmöglichkeiten sind:

| Einstellung | Zweck |
| --- | --- |
| `--data-dir` | Geschützter Datenordner einschließlich Dokumentdateien |
| `--host` | Bindeadresse; Netzwerkbindung bewusst durch den Betreiber festlegen |
| `--port` | Anwendungsport; Standard ist `8765` |
| `--no-browser` | Server ohne automatisches Öffnen eines lokalen Browsers |
| `--ssl-certfile`, `--ssl-keyfile` | Lokales TLS-Zertifikat und zugehöriger privater Schlüssel |
| `KINDT_ALLOWED_HOSTS` | Die tatsächlich verwendeten eigenen Hostnamen erlauben |
| `KINDT_SECURE_COOKIES=1` | Sichere Sitzungscookies für HTTPS |
| `KINDT_DATABASE_URL` | Sicher konfigurierte PostgreSQL-Verbindung |

Für die Netzwerkbindung Zertifikat und Schlüssel bereitstellen, sichere Cookies aktivieren und erlaubte Hostnamen passend zum Zertifikat konfigurieren. Clients müssen der Zertifikatskette vertrauen; Zertifikatswarnungen vor dem produktiven Einsatz beheben. Die Anwendung beschafft oder erneuert keine Zertifikate im Internet.

Beispielstruktur für Windows, nachdem die eigene sichere Umgebung eingerichtet wurde:

```text
KindtEnterpriseSuiteServer.exe --data-dir "<geschützter-Datenordner>" --host 0.0.0.0 --no-browser --ssl-certfile "<Zertifikatdatei>" --ssl-keyfile "<Schlüsseldatei>"
```

Unter Linux entsprechend den nativen Starter `./KindtEnterpriseSuiteServer/KindtEnterpriseSuiteServer` mit denselben Optionen verwenden. Die Bindung an alle Netzwerkschnittstellen nur in einer bewusst eingerichteten Betriebsumgebung wählen. Firewall, Dienstverwaltung, Zertifikatsvertrauen und Betriebssystemrechte richtet der Betreiber ein.

Auf den LAN-Clients im Browser `https://<eigener-zertifikatsgültiger-Servername>:8765` öffnen. Bei abweichendem `--port` den entsprechend konfigurierten Port verwenden. Der Servername muss zum Zertifikat und zu `KINDT_ALLOWED_HOSTS` passen; `0.0.0.0` ist die Bindeadresse des Servers und keine Zieladresse für Clients.

Die Datenbankverbindung mit Zertifikatsprüfung `sslmode=verify-full` und passender CA einrichten. Zugangsdaten sicher lokal bereitstellen, etwa über eine geschützte libpq-Passwortdatei; nicht in Versionskontrolle oder Supportberichte übernehmen. Reverse-Proxy-Betrieb benötigt eine gesondert geprüfte Konfiguration.

## Sicherungen und laufender Betrieb

SQLite-Sicherungen über **Core → Sicherungen** erstellen und auf einem getrennten Datenträger aufbewahren. Sie enthalten Datenbank und Dokumente. Für PostgreSQL den mitgelieferten nativen Sicherungs-/Wiederherstellungspfad und die separat bereitgestellten Werkzeuge nach der ausführlichen Paketdokumentation verwenden; die SQLite-Schaltflächen ersetzen ihn nicht.

Backups sind unverschlüsselt. Dateirechte, Datenträgerverschlüsselung, Aufbewahrung und regelmäßige Wiederherstellungsprüfungen liegen beim Betreiber. Vor Updates die [Upgradeanleitung](UPGRADE.md) lesen.
