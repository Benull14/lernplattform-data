# LF7 Daten hochladen

## Vorbereitung

Dieses Lernfeld ist noch nicht konfiguriert. Folge diesen Schritten:

## 1. questions.json erstellen

📁 **Datei:** `lf7/questions.json`

**Schritte:**

1. Erstelle eine `questions.json` Datei mit der Struktur aus LF6
2. Passe die Fragen für LF7 an
3. Lade sie auf GitHub hoch: `lf7/questions.json`

## 2. PDF-Skripte hochladen

📁 **Zielordner:** `lf7/scripts/`

**Schritte:**

1. Sammle alle PDF-Skripte für LF7
2. Lade sie in `lf7/scripts/` hoch
3. Notiere die Dateinamen (werden für die Konfiguration benötigt)

## 3. Lernplattform konfigurieren

Nach dem Upload musst du `src/config/accessCodes.ts` im Lernplattform-Projekt aktualisieren:

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
    // Füge hier weitere Skripte hinzu
  ],
  active: true
}
```

## URLs

**JSON:**

```
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf7/questions.json
```

**PDFs:**

```
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf7/scripts/{filename}.pdf
```
