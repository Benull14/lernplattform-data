# GitHub Repository Setup - Schritt für Schritt

## ✅ Schritt 1: Repository auf GitHub erstellen

1. Gehe zu: https://github.com/new
2. **Repository-Name:** `lernplattform-data`
3. **Beschreibung:** "Kursinhalte für die Lernplattform"
4. **Sichtbarkeit:** ⚠️ **PUBLIC** (sehr wichtig!)
5. ✅ Haken bei "Add a README file" NICHT setzen (wir haben schon eins)
6. Klicke auf "Create repository"

## ✅ Schritt 2: Lokale Dateien vorbereiten

Die Verzeichnisstruktur ist bereits erstellt:

```
lernplattform-data/
├── README.md ✅
├── lf6/
│   ├── UPLOAD_ANLEITUNG.md ✅
│   └── scripts/ (leer)
└── lf7/
    ├── UPLOAD_ANLEITUNG.md ✅
    └── scripts/ (leer)
```

## ✅ Schritt 3: Repository initialisieren und hochladen

### Option A: Via Git (empfohlen)

```bash
# Im Ordner Lernplattform-data:
git init
git add .
git commit -m "Initial commit: Repository structure"
git branch -M main
git remote add origin https://github.com/Benull14/lernplattform-data.git
git push -u origin main
```

### Option B: Via GitHub Web Interface

1. Navigiere zu deinem neuen Repository
2. Klicke auf "uploading an existing file"
3. Ziehe alle Dateien und Ordner in das Upload-Fenster
4. Commit message: "Initial commit: Repository structure"
5. Klicke "Commit changes"

## ✅ Schritt 4: LF6 Daten kopieren

### questions.json

1. **Öffne** im Lernplattform-Projekt: `public/data/lf6-questions.json`
2. **Kopiere** den gesamten Inhalt
3. **Gehe** zum GitHub Repository
4. **Erstelle** neue Datei: `lf6/questions.json`
5. **Füge** den JSON-Inhalt ein
6. **Commit:** "Add LF6 questions"

### PDF-Skripte

1. **Gehe** zum GitHub Repository → `lf6/scripts/`
2. **Klicke** "Add file" → "Upload files"
3. **Wähle** aus dem Lernplattform-Projekt `public/scripts/`:
   - IT-Serviceanfragen-Annahme-Bearbeitung-und-Steuerung.pdf
   - IT-Serviceanfragen-analysieren-und-Losungen-erarbeiten.pdf
   - Servicearten-und-Serviceanforderungen-im-IT-Bereich.pdf
4. **Commit:** "Add LF6 scripts"

## ✅ Schritt 5: URLs testen

Warte 1-2 Minuten (GitHub Cache) und teste diese URLs im Browser:

**JSON:**

```
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/questions.json
```

**PDFs (Beispiel):**

```
https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/scripts/IT-Serviceanfragen-Annahme-Bearbeitung-und-Steuerung.pdf
```

Die URLs sollten die Dateien direkt anzeigen/herunterladen.

## ✅ Schritt 6: In der Lernplattform testen

1. Öffne die Lernplattform
2. Logge dich mit Code `LF62025` ein
3. Prüfe, ob die Daten laden
4. Teste den Tab "Lernmaterialien"
5. Teste "Anzeigen" und "Herunterladen" für die PDFs

## 🆘 Troubleshooting

### URLs funktionieren nicht

- ✅ Repository ist **public**?
- ✅ Branch heißt `main` (nicht `master`)?
- ⏰ 1-2 Minuten gewartet?

### PDFs laden nicht

- ✅ Dateinamen korrekt (Groß-/Kleinschreibung)?
- ✅ Im richtigen Ordner (`lf6/scripts/`)?
- 🔗 Raw-URL direkt im Browser testen?

### JSON lädt nicht

- ✅ JSON-Syntax korrekt?
- 🔍 Browser-Konsole auf Fehler prüfen?
- 🔗 Raw-URL direkt im Browser testen?

## 📝 Cache leeren (falls nötig)

Die Lernplattform cached GitHub-Daten für 5 Minuten:

1. Browser-Konsole öffnen (F12)
2. `localStorage.clear()` ausführen
3. Seite neu laden

---

**Hinweis:** Die Ordner `lf6/scripts/` und `lf7/scripts/` sind leer. Die tatsächlichen PDF-Dateien müssen aus dem Lernplattform-Projekt kopiert werden!
