# AI Drone – Automated Delivery

Documentation for the project **"Automated drone delivery with AI"**.

📖 **[View the online documentation](https://ki-drohnen-ss26.github.io/project-docs/)**

## Local development

### Prerequisites

- Python 3.10 or newer
- pip

### Setup

```bash
# Clone the repository
git clone https://github.com/ki-drohnen-ss26/project-docs.git
cd project-docs

# Create a virtual environment (recommended)
python -m venv .venv
source .venv/bin/activate   # Linux/macOS
# .venv\Scripts\activate    # Windows

# Install dependencies
pip install -r requirements.txt
```

### Local dev server

```bash
mkdocs serve
```

The documentation is then available at <http://127.0.0.1:8000>. Changes to Markdown files are picked up automatically (hot reload).

### Build the site

```bash
mkdocs build
```

The static site is generated in the `site/` directory.

## Deployment

On every push to the `main` branch, the documentation is automatically built and published to GitHub Pages via GitHub Actions. The workflow is defined in `.github/workflows/deploy.yml`.

### One-time setup on GitHub

1. In the repository under **Settings → Pages**, set the source to **GitHub Actions**.
2. The first push to `main` will trigger the deployment.

## Structure

```
.
├── .github/workflows/   # CI/CD (GitHub Actions)
├── docs/                # Markdown source files
│   ├── assets/          # images, CSS, JS
│   ├── hardware/
│   ├── software/
│   └── ...
├── mkdocs.yml           # MkDocs configuration
└── requirements.txt     # Python dependencies
```

## Contributing

Content is written in Markdown. Useful references:

- [MkDocs Material – Reference](https://squidfunk.github.io/mkdocs-material/reference/)
- [Markdown Cheatsheet](https://www.markdownguide.org/cheat-sheet/)
- [Mermaid – Diagrams](https://mermaid.js.org/)

For weekly status entries, see the [Project Journal](docs/history/index.md) and the template at `docs/history/_template.md`.
