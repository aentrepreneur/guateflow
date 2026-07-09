# GuateFlow — Architecture

## System Overview

GuateFlow is a multi-component platform composed of:

1. **VSCode Extension** — primary user interface
2. **Core API Layer** — shared business logic
3. **External Integrations** — OCDS, SAT, OCR, Lemon Squeezy

## Component Architecture

### VSCode Extension

```text
vscode-ext/
├── src/
│   ├── free/              Free-tier features
│   │   ├── dpi-validator.ts    NIT/DPI validation via SAT
│   │   ├── labor-calculator.ts Labor law calculations
│   │   ├── formatters.ts       GT-specific formatters
│   │   └── status-bar.ts       Live tender count
│   ├── pro/               Pro-tier features (license-gated)
│   │   ├── guatecompras/       Tender search + filtering
│   │   ├── ocr/                Document analysis
│   │   └── license/            Key validation
│   └── extension.ts       Entry point
├── tests/
└── package.json
```

### Data Flow

```text
User (VSCode)
  │
  ├─► DPI Validator ──► SAT Portal ──► Validation Result
  ├─► Labor Calc ──► Local Formulas ──► Calculation
  ├─► Tender Search ──► OCDS API ──► Results List
  ├─► OCR Pipeline ──► Tesseract/GPT ──► Extracted Data
  └─► License ──► Lemon Squeezy ──► Activation Status
```

### API Integration Points

| Integration | Protocol | Auth | Rate Limit |
|-------------|----------|------|------------|
| OCDS (Guatecompras) | REST/JSON | Public | Throttled |
| SAT Portal | Browser automation | CAPTCHA manual | Per-session |
| OCR Engine | Local Tesseract + GPT API | API key (Pro) | Token-based |
| Lemon Squeezy | REST/JSON | License key | Per-activation |

### Tier System

| Feature | Free | Pro |
|---------|------|-----|
| Labor calculator | ✅ | ✅ |
| DPI/NIT validator | ✅ | ✅ |
| GT formatters | ✅ | ✅ |
| Status bar | ✅ | ✅ |
| Tender search | ❌ | ✅ |
| Tender details | ❌ | ✅ |
| OCR analysis | ❌ | ✅ |
| Export & reports | ❌ | ✅ |

## Security Considerations

- License keys validated server-side via Lemon Squeezy
- SAT portal interaction requires manual CAPTCHA (no automation abuse)
- No PII stored locally
- API keys scoped to Pro features only
