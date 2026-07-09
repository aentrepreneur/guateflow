<div align="center">

# GuateFlow

Guatecompras intelligence platform — tender search, OCR analysis, and labor calculator for Guatemala's public procurement system

![Status](https://img.shields.io/badge/status-Stable-28a745?style=flat-square)
[![License](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](LICENSE)
![Updated](https://img.shields.io/github/last-commit/aentrepreneur/guateflow?style=flat-square)

</div>

## Overview

GuateFlow is a multi-tool platform for navigating Guatemala's public procurement ecosystem (Guatecompras). It combines real-time tender search, OCR document analysis, labor cost calculation, and a VSCode extension — giving contractors, consultants, and businesses a unified interface for finding and assessing public contract opportunities.

## Features

| Feature | Tier | Description |
|---------|------|-------------|
| Tender Search | Free | Search and filter Guatecompras tenders via OCDS API |
| OCR Analysis | Pro | Automated document extraction and bid analysis |
| Labor Calculator | Free | Bono 14, Aguinaldo, Indemnizacion, Vacaciones |
| NIT/DPI Validator | Free | Tax ID validation via SAT portal |
| Status Bar Monitor | Free | Live tender count in VSCode status bar |
| VSCode Extension | Free + Pro | Full-featured extension in VS Code Marketplace |
| License Management | Pro | License key validation via Lemon Squeezy |

## Architecture

```text
┌─────────────────────────────────────────────┐
│                VSCode Extension              │
│  ┌──────────┐ ┌──────────┐ ┌─────────────┐  │
│  │  Search  │ │   OCR    │ │   Labor Calc │  │
│  └────┬─────┘ └────┬─────┘ └──────┬──────┘  │
│       │             │              │          │
│  ┌────┴─────────────┴──────────────┴──────┐  │
│  │           Core API Layer                │  │
│  └──────────────────┬─────────────────────┘  │
└─────────────────────┼────────────────────────┘
                      │
         ┌────────────┼────────────┐
         ▼            ▼            ▼
   ┌──────────┐ ┌──────────┐ ┌──────────┐
   │ OCDS API │ │ OCR Engine│ │ SAT Portal│
   │(Guatec.) │ │ (Tesseract│ │ (DGT/SAT) │
   │          │ │  + GPT)  │ │           │
   └──────────┘ └──────────┘ └──────────┘
```

## Quick Start

### VSCode Extension

```bash
# Install from VS Code Marketplace
# Search: "GuateFlow"

# Or build from source
git clone https://github.com/aentrepreneur/guateflow.git
cd guateflow/vscode-ext
npm install
vsce package
code --install-extension guateflow-0.1.0.vsix
```

### License Activation

```bash
# Free tier: no license needed
# Pro tier: activate via command palette
# Cmd+Shift+P -> "GuateFlow: Activate License"
```

## Naming Convention

| Context | Name |
|---------|------|
| VS Code Marketplace ID | `guateflow` |
| Display Name | `GuateFlow` (capital G, capital F) |
| GitHub Repository | `guateflow` |
| Landing Domain | `guateflow.dev` |
| Support Email | `guateflow@aentrepreneur.dev` |

## Documentation

- `docs/guateflow-guide.md` — complete product guide with roadmap, naming, and marketing
- `docs/architecture.md` — system architecture and data flow
- `docs/use-cases.md` — user profiles and scenarios
- `examples/` — search commands and workflow examples

## Roadmap

| Phase | Timeline | Scope |
|-------|----------|-------|
| **FREE** | Week 1 | Scaffolding, DPI/NIT validator, labor calculator, status bar |
| **PRO** | Week 2 | Guatecompras search, tender details, NIT integration |
| **PRO OCR** | Week 3 | Document OCR, bid analysis, Q&A |

## License

MIT — see [LICENSE](LICENSE)

## Author

Angel Esquivel — [@aentrepreneur](https://github.com/aentrepreneur)
