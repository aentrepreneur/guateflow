# GuateFlow — Example Search Commands

## Basic Tender Search

```bash
# Search by keyword
GuateFlow: Search Tenders -> "construccion hospital"

# Filter by entity
GuateFlow: Search by Entity -> "Ministerio de Salud"

# Filter by category
GuateFlow: Filter by Category -> "Construccion"
```

## Advanced Filters

```bash
# Budget range
GuateFlow: Search Tenders -> budget:>100000 category:construccion

# Date range
GuateFlow: Search Tenders -> from:2026-01-01 to:2026-06-30

# Combined
GuateFlow: Search Tenders -> "equipo medico" budget:>50000 entity:IGSS
```

## Labor Calculator Examples

```bash
# Calculate Bono 14
GuateFlow: Labor Calculator -> bono14 salary:3000 months:12

# Calculate Aguinaldo
GuateFlow: Labor Calculator -> aguinaldo salary:3000 months:12

# Calculate full package
GuateFlow: Labor Calculator -> full salary:3000 months:12 position:tecnico
```

## OCR Analysis

```bash
# Open tender with PDF attachments
GuateFlow: Open Tender -> NOG-123456

# Extract requirements
GuateFlow: Analyze Document -> "technical specifications"

# Ask specific questions
GuateFlow: Ask About Tender -> "What are the insurance requirements?"
```

## Status Bar Monitor

```bash
# Configure refresh interval
GuateFlow: Settings -> Status Bar Refresh: 15 minutes

# Filter status bar count
GuateFlow: Settings -> Status Bar Filter: category:construccion

# Click status bar to open tender browser
📊 47 tenders today -> Cmd+Shift+P -> "GuateFlow: Open Tender Browser"
```

## Export Formats

```bash
# Export tender list
GuateFlow: Export Tenders -> CSV

# Export analysis report
GuateFlow: Export Analysis -> PDF

# Export labor calculation
GuateFlow: Export Calculation -> JSON
```
