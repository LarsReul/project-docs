# KI-Drohne – Automatisierte Auslieferung

Dokumentation zum Projekt **"Automatisierte Drohnen-Auslieferung mit KI"**.

📖 **[Zur Online-Dokumentation](https://<github-username>.github.io/<repo-name>/)**

## Lokale Entwicklung

### Voraussetzungen

- Python 3.10 oder neuer
- pip

### Setup

```bash
# Repository klonen
git clone https://github.com/<github-username>/<repo-name>.git
cd <repo-name>

# Virtuelles Environment anlegen (empfohlen)
python -m venv .venv
source .venv/bin/activate  # Linux/macOS
# .venv\Scripts\activate    # Windows

# Abhängigkeiten installieren
pip install -r requirements.txt
```

### Lokaler Entwicklungsserver

```bash
mkdocs serve
```

Die Doku ist dann unter <http://127.0.0.1:8000> erreichbar. Änderungen an Markdown-Dateien werden automatisch übernommen (Hot Reload).

### Site bauen

```bash
mkdocs build
```

Die statische Site wird im `site/`-Verzeichnis erzeugt.

## Deployment

Bei jedem Push auf den `main`-Branch wird die Doku automatisch via GitHub Actions auf GitHub Pages veröffentlicht. Die Konfiguration findet sich in `.github/workflows/deploy.yml`.

### Einmalige Einrichtung in GitHub

1. Im Repository unter **Settings → Pages**: Source auf **GitHub Actions** stellen.
2. Der erste Push auf `main` triggert das Deployment.

## Struktur

```
.
├── .github/workflows/   # CI/CD (GitHub Actions)
├── docs/                # Markdown-Quelldateien der Doku
│   ├── assets/          # Bilder, CSS, JS
│   ├── hardware/
│   ├── software/
│   └── ...
├── mkdocs.yml           # MkDocs-Konfiguration
└── requirements.txt     # Python-Abhängigkeiten
```

## Mitwirken

Inhalte werden in Markdown geschrieben. Hilfreiche Links:

- [MkDocs Material – Reference](https://squidfunk.github.io/mkdocs-material/reference/)
- [Markdown Cheatsheet](https://www.markdownguide.org/cheat-sheet/)
- [Mermaid – Diagramme](https://mermaid.js.org/)
