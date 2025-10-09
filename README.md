# Lernplattform-Data

Dieses Repository enthält die Kursinhalte für die Lernplattform.

## Struktur

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
│       └── (PDFs hier hochladen)
└── README.md
```

## Verwendung

Die Daten werden über GitHub Raw URLs von der Lernplattform geladen:

- Questions JSON: `https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/questions.json`
- PDF-Skripte: `https://raw.githubusercontent.com/Benull14/lernplattform-data/main/lf6/scripts/{filename}.pdf`

## Hinweise

- Das Repository muss **public** sein, damit die Raw URLs funktionieren
- Nach dem Upload 1-2 Minuten warten (GitHub Cache)
- Dateinamen beachten (Groß-/Kleinschreibung!)
