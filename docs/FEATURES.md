# Funktionen und Arbeitsbereiche

Die deutsche Oberfläche verbindet Fachmodule und persönliche Arbeitsbereiche mit einer gemeinsamen lokalen Datenhaltung. Der hier beschriebene Stand ist das vorhandene Programm 1.2.0; das Preview-Label führt keine neuen Funktionen ein.

## Fachmodule

| Arbeitsbereich | Vorhandener Umfang |
| --- | --- |
| Core | Unternehmen und Benutzer, Rollen, freigeschaltete Module, Audit sowie SQLite-Sicherungen |
| FinanceForge | Kontakte, Angebote und Rechnungen; Rechnungsvorlagen; explizit erzeugte wiederkehrende Entwürfe; interne Mahnstufen; offene Posten, Zahlungen und Finanzberichte |
| PeopleForge | Personal, Urlaub, Abwesenheiten und Zeiten; Schichtplanung, persönlicher Kalender, Self-Service und Soll-/Ist-Vergleich |
| OfficeForge | Versionierte Dokumentdateien, Aufgaben, unabhängige Freigaben und Termine |
| AssetForge | Inventar, Softwarelizenzen und Wartungen |
| ServiceForge | Tickets, Kommentare, Verlauf und Wissensartikel |
| Executive Center | Persönliche Dashboards, Diagramme, Filter und PDF-/CSV-Berichte |
| Workflow-Designer | Begrenzte azyklische Abläufe mit Bedingungen, lokalen Aufgaben und Hinweisen sowie Ausführungsprotokollen |

Wiederkehrende Rechnungen entstehen durch eine ausdrückliche Benutzeraktion als Entwurf. Interne Mahnverläufe bewirken keinen Versand. Der Workflow-Designer führt keine beliebigen Programme oder Netzwerkaktionen aus; KI-Funktionen bleiben deaktiviert.

## Neu in 1.2

### Persönliche Darstellung und Hinweise

Sechs Designvorlagen einschließlich des unveränderten Standard-Navy, native Farbwähler und direkte Felder für Hintergrund- und Akzentfarbe im Format `#RRGGBB`. Gültige Änderungen erscheinen unmittelbar als Vorschau. Ungültiger oder unvollständiger Text sperrt Speichern; Verwerfen stellt den zuletzt geladenen Stand wieder her. Gespeicherte Einstellungen gehören ausschließlich zum angemeldeten Konto.

Benachrichtigungskategorien und Fristenvorlauf sind persönlich einstellbar. Abmelden und Sitzungsablauf entfernen die persönliche Farbpalette und den bisherigen Arbeitsbereich.

### Dokumentarbeitsplatz

Kategorien, Vorlagen und private oder gemeinsame Dokumente ergänzen die versionierte Ablage. Eine Vorlage erzeugt einen Dokumententwurf mit erster Textdateiversion. Der Arbeitsplatz zeigt Versionen, Dateigrößen und SHA-256 sowie begrenzte Textvorschau und Versionsvergleich für TXT, CSV, DOCX und XLSX.

Archivieren erhält Originale und Historie; Wiederherstellen aktiviert das Dokument erneut. Die Suche umfasst erlaubte Metadaten und unterstützte Inhalte der aktuellen Dateiversion. PDF und Bilder bieten Metadaten und Originaldownload; OCR ist nicht enthalten.

### Unternehmenskalender

Tages-, Wochen- und Monatsansicht vereinen Termine, Aufgabenfristen, Urlaub, Abwesenheiten, Schichten, Projekte und Meilensteine. Persönliche und gemeinsame Ansichten, Typfilter und Direktnavigation führen zum jeweils berechtigten Vorgang. Neue Zeitpunkte verwenden explizite Zeitzonen.

### Benachrichtigungszentrale

Persönliche Gelesen-/Ungelesen-Markierungen, Filter und Direktnavigation beziehen sich auf die jeweils erlaubten Vorgänge. Das Lesen eines gemeinsamen Hinweises durch einen Benutzer verändert die persönliche Lesemarke eines anderen Benutzers nicht.

### Globale Unternehmenssuche

Ab zwei Zeichen werden berechtigte Datensätze und begrenzte Dokumenttextausschnitte durchsucht. Modul- und Typfilter sowie Direktnavigation helfen beim Öffnen des richtigen Vorgangs. Weitere Suchabschnitte werden ausdrücklich ausgewiesen; eine begrenzte Abfrage wird nicht als vollständiger Trefferbestand dargestellt.

## Zugriffe und Zusammenarbeit

Rollen, Mandanten, Modulfreigaben und private Sichtbarkeit werden serverseitig geprüft. Mitarbeiter sehen bei Personaldaten die eigenen Zuordnungen. Private Dokumente und Termine sind für Eigentümer und Administration zugänglich; sie sind kein gegenüber der Administration abgeschotteter Tresor. Gemeinsame Daten bleiben für passend berechtigte Konten erreichbar. Versionsprüfungen erkennen konkurrierende Änderungen.

Die [Einschränkungen](LIMITATIONS.md) erläutern Format-, Fach- und Betriebsgrenzen.