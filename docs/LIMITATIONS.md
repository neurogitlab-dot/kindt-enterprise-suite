# Grenzen und Betriebsbedingungen

## Preview, Lizenz und Weitergabe

Die kostenlose Edition ist Closed Source und für nichtkommerzielle Nutzung bestimmt. Kommerzielle Nutzung Dritter benötigt Erlaubnis. Die unveränderte Kindt-Lizenz, die ausdrücklich benannten Produktbedingungen und eigenständige Drittanbieterrechte gelten gemeinsam. Linux-Vertriebshüllen sind für die öffentliche Auswahl vorbereitet; Windows bleibt gesperrt. Keine bereits erfolgte Veröffentlichung wird behauptet.

Der frühere persönliche Linux-CFFI-Buildpfadbefund wurde durch neutralen Neubau und gezielte Abnahme geschlossen. Die jetzigen äußeren Lieferpakete enthalten genau die geprüften unveränderten Innenarchive. Es wird keine vollständige Geheimnisfreiheit, Nicht-Dekompilierbarkeit oder generelle Eignung für jede Distribution zugesagt. [Weitergabe](DISTRIBUTION.md), [Prüfstand](CLEARANCE.md).

## Plattform und Betrieb

- Windows: Windows 10 oder neuer, x64. Linux: tatsächlich abgenommen auf Ubuntu 26.04.1 LTS x86-64 mit glibc 2.43; andere Systeme sind dadurch nicht abgedeckt.
- Die Oberfläche läuft im vorhandenen lokalen Browser, geöffnet durch einen nativen Starter. Ein eingebetteter Tauri-Webview gehört nicht zu diesem Lieferstand.
- Ein Suite-Prozess je Datenverzeichnis beziehungsweise Datenbankschema mit mehreren Browserclients ist der geprüfte Betriebsmodus. Hochverfügbarkeit und mehrere unabhängige Anwendungsschreiber werden nicht zugesagt.
- SQLite ist für lokale Daten und geringe Last vorgesehen. Eine SQLite-Datei auf einer Netzwerkfreigabe darf nicht als gemeinsame Datenbank verwendet werden.
- PostgreSQL-Server, passende Sicherungswerkzeuge, Zertifikate, Vertrauensketten, Dienstverwaltung und Firewall bleiben Betreiberaufgaben. Vollständig geprüft wurde PostgreSQL 18.6.
- Die Anwendung benötigt für Kernfunktionen nach vorbereiteter Installation kein Internet. Der Anwendungsmodus `--offline` ersetzt keine vom Betriebssystem durchgesetzte Netzwerkisolation.

## Fachliche Grenzen

Die Suite ersetzt keine vollständige Steuer-, Finanz- oder Lohnbuchhaltung. Die DATEV-Funktion erzeugt eine vorbereitende CSV mit fachlich zu ergänzenden Zuordnungen; sie ist kein fertiger EXTF-Buchungsstapel und besitzt keine DATEV-Zertifizierung. Strukturierte E-Rechnungen und revisionssichere Archivierung gehören nicht zum Funktionsumfang.

Rechnungsvorlagen und Wiederholungen erzeugen ausdrücklich angeforderte Entwürfe. Es gibt keinen automatischen Rechnungs- oder Mahnversand. Personalstunden, Schichten und Soll-/Ist-Werte sind technische Verwaltungsfunktionen; sie prüfen kein Arbeitszeitrecht und berechnen keine Entgelte oder rechtsverbindlichen Zeitkonten.

Workflows sind begrenzte lokale Abläufe. Sie bieten keine beliebige Programmausführung, keine Cloud-/KI-Aktion und keine automatische Fortsetzung einer Geschäftsfreigabe nach einer unabhängigen Entscheidung.

## Dokumente und Suche

Textvorschau, Textvergleich und Volltextsuche unterstützen begrenzt TXT, CSV, DOCX und XLSX. PDF und Bilder bieten Metadaten und Originaldownload, ohne OCR oder eingebettete Dokumentdarstellung. Makros, externe Beziehungen und ausführbare Inhalte werden nicht ausgewertet.

Die Dokumentverarbeitung begrenzt Dateigrößen, Office-Archivmitglieder, extrahierten Text und Suchabschnitte. Hinweise auf gekürzte Inhalte oder weitere Abschnitte sind zu beachten. Für die vollständige Suche müssen die angebotenen Abschnitte durchlaufen werden; Inhalte hinter einer ausgewiesenen Textgrenze bleiben unerschlossen. Schutzprüfungen ersetzen keinen Virenscanner.

## Sicherheit und Nachweisgrenzen

Backups sind unverschlüsselt. Geschützte Dateisystemrechte, sichere Aufbewahrung, Datenträgerverschlüsselung und Wiederherstellungsübungen mit eigenen Daten liegen beim Betreiber. Es werden weder Codesignatur noch unabhängige Penetrationstest-, Last- oder Barrierefreiheitszertifizierung zugesagt.

Die vorhandene Windows-Abnahme verwendet lokale Offline-Anwendungseinstellungen und geprüfte HTTPS-Ziele; sie belegt keine physische Abschaltung aller Windows-Netzwerkschnittstellen. Die Linux-Abnahme verwendete einen getrennten Netzwerkraum ohne Internetroute. Sie ersetzt keinen Versuch an einem zweiten physischen Arbeitsplatz.

Die direkte Linux-GUI-Abnahme umfasste manuelle Anmeldungen, HEX-Eingaben und einen Suchbegriff. Automatisierte Tastaturübertragung war dabei wirkungslos; eine direkte Linux-Prüfung ungültiger HEX-Eingaben und eine vollständige Tastaturprüfung werden nicht behauptet. Sichtprüfungen sind kein vollständiger Pixel- oder Barrierefreiheitsnachweis. Komponenten-/API-Prüfungen und sichtbare Bedienung bleiben getrennte Nachweise.

Ein Upgrade benötigt eine vollständige vorherige Sicherung. Rückfall bedeutet Rückkehr zur alten Programmversion mit dem passenden alten Datenstand; nachträgliche Änderungen werden dabei nicht erhalten. Siehe [Upgrade](UPGRADE.md).