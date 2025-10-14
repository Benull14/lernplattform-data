# GitHub Repository Setup für Lernplattform-Daten

## Übersicht

Dieses Dokument beschreibt, wie Sie das GitHub-Repository `lernplattform-data` einrichten, um Kursinhalte extern zu hosten.

## Repository-Struktur

Erstellen Sie ein öffentliches Repository unter: `https://github.com/Benull14/lernplattform-data`

### Verzeichnisstruktur

```
lernplattform-data/
├── lf6/
│   ├── questions.json
│   └── scripts/
│       ├── IT-Serviceanfragen-Annahme-Bearbeitung-und-Steuerung.pdf
│       ├── IT-Serviceanfragen-analysieren-und-Losungen-erarbeiten.pdf
│       └── Servicearten-und-Serviceanforderungen-im-IT-Bereich.pdf
├── lf7/
│   ├── questions.json
│   └── scripts/
│       ├── skript1.pdf
│       └── skript2.pdf
└── README.md
```

## Schritt-für-Schritt Anleitung

### 1. Repository erstellen

1. Gehen Sie zu https://github.com/new
2. Repository-Name: `lernplattform-data`
3. Beschreibung: "Kursinhalte für die Lernplattform"
4. Sichtbarkeit: **Public** (damit GitHub Raw URLs funktionieren)
5. Klicken Sie auf "Create repository"

### 2. LF6-Daten hochladen

Für den LF6-Kurs müssen Sie folgende Dateien hochladen:

#### questions.json

Kopieren Sie den Inhalt aus Ihrer lokalen Datei:
- Quelle: `public/data/lf6-questions.json`
- Ziel: `lf6/questions.json` im GitHub-Repository

#### PDF-Skripte

Kopieren Sie die folgenden PDFs aus dem lokalen Ordner `public/scripts/`:
- `IT-Serviceanfragen-Annahme-Bearbeitung-und-Steuerung.pdf`
- `IT-Serviceanfragen-analysieren-und-Losungen-erarbeiten.pdf`
- `Servicearten-und-Serviceanforderungen-im-IT-Bereich.pdf`

Laden Sie diese in den Ordner `lf6/scripts/` im GitHub-Repository hoch.

### 3. Dateien hochladen (Web-Interface)

1. Navigieren Sie zu Ihrem Repository
2. Klicken Sie auf "Add file" > "Create new file"
3. Für die questions.json:
   - Dateiname: `lf6/questions.json` (Der `/` erstellt automatisch den Ordner)
   - Fügen Sie den JSON-Inhalt ein
   - Commit mit Nachricht: "Add LF6 questions"

4. Für die PDFs:
   - Klicken Sie auf "Add file" > "Upload files"
   - Navigieren Sie zu `lf6/scripts/` (erstellen Sie den Ordner falls nötig)
   - Laden Sie alle drei PDFs hoch
   - Commit mit Nachricht: "Add LF6 scripts"

### 4. GitHub Raw URLs verifizieren

Nach dem Upload sollten folgende URLs erreichbar sein:

#### Questions JSON:
```
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/questions.json
```

#### PDF-Skripte:
```
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/scripts/IT-Serviceanfragen-Annahme-Bearbeitung-und-Steuerung.pdf
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/scripts/IT-Serviceanfragen-analysieren-und-Losungen-erarbeiten.pdf
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/scripts/Servicearten-und-Serviceanforderungen-im-IT-Bereich.pdf
```

### 5. Testen

1. Öffnen Sie die Lernplattform
2. Loggen Sie sich mit dem Access-Code `LF62025` ein
3. Die App sollte jetzt die Daten von GitHub laden
4. Klicken Sie auf den Tab "Lernmaterialien"
5. Sie sollten die drei PDF-Skripte sehen können
6. Testen Sie "Anzeigen" und "Herunterladen" für jedes Skript

## Weitere Kurse hinzufügen

Um weitere Kurse (z.B. LF7) hinzuzufügen:

1. Erstellen Sie einen neuen Ordner im Repository: `lf7/`
2. Laden Sie `questions.json` hoch
3. Erstellen Sie `scripts/` Unterordner
4. Laden Sie die PDFs hoch
5. Aktualisieren Sie `src/config/accessCodes.ts` mit den neuen URLs:

```typescript
{
  code: "LF72025",
  name: "LERNFELD 7",
  description: "Beschreibung für LF7",
  dataFile: "/data/lf7-questions.json", // Fallback
  githubJsonUrl: "https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf7/questions.json",
  githubScriptsFolderUrl: "https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf7/scripts",
  scriptsMetadata: [
    {
      title: "Skript 1 Titel",
      filename: "skript1.pdf",
      description: "Beschreibung"
    },
    // ... weitere Skripte
  ],
  active: true
}
```

## Vorteile dieser Lösung

1. **Kein Build erforderlich**: Content-Updates ohne App-Deployment
2. **Kleinere Bundle-Größe**: PDFs und große JSONs werden nicht gebundelt
3. **Einfache Content-Verwaltung**: GitHub als CMS
4. **Versionierung**: Git-History für alle Änderungen
5. **Kostenloses CDN**: GitHub Raw als Hosting
6. **Fallback-Mechanismus**: Funktioniert auch mit lokalen Dateien

## Troubleshooting

### URLs funktionieren nicht
- Stellen Sie sicher, dass das Repository **public** ist
- Überprüfen Sie, dass der Branch `main` heißt (nicht `master`)
- Warten Sie 1-2 Minuten nach dem Upload (GitHub Cache)

### PDFs laden nicht
- Überprüfen Sie die Dateinamen (Groß-/Kleinschreibung beachten!)
- Stellen Sie sicher, dass die PDFs im korrekten Ordner sind
- Testen Sie die Raw-URL direkt im Browser

### JSON lädt nicht
- Validieren Sie die JSON-Syntax mit einem JSON-Validator
- Überprüfen Sie die Konsole auf Fehler
- Testen Sie die Raw-URL direkt im Browser

## Cache

Die App cached GitHub-Daten für 5 Minuten in localStorage. Um den Cache zu leeren:
1. Öffnen Sie die Browser-Konsole
2. Führen Sie aus: `localStorage.clear()`
3. Laden Sie die Seite neu
