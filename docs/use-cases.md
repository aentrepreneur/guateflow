# GuateFlow — Use Cases

## User Profiles

### Independent Contractor
- Monitors new tenders daily for relevant opportunities
- Uses labor calculator to estimate staff costs for bids
- Validates NIT/DGT status before submitting proposals
- **Primary features:** Tender search, labor calculator, NIT validator

### Consulting Firm
- Team of 3-5 analysts tracking multiple tender categories
- Uses OCR to extract requirements from attached PDFs
- Exports tender summaries for internal review meetings
- **Primary features:** OCR analysis, tender filters, export

### Government Auditor
- Verifies contractor compliance using DPI/NIT validator
- Cross-references labor calculations in submitted bids
- Archives tender documentation for audit trails
- **Primary features:** NIT validator, labor calculator, document viewer

### Legal Advisor
- Reviews procurement terms and conditions via OCR
- Flags irregular clauses using keyword analysis
- Maintains historical record of awarded contracts
- **Primary features:** OCR analysis, tender history

## Typical Workflows

### Workflow 1: Daily Tender Monitoring

```bash
1. Open VSCode with GuateFlow extension
2. Status bar shows "📊 47 tenders today"
3. Click status bar → opens tender browser
4. Filter by category: "Construction"
5. Sort by publication date descending
6. Open tender details → OCR extracts key specs
7. Use labor calculator to estimate project costs
8. Save for later review
```

### Workflow 2: Bid Preparation

```bash
1. Search: "hospital equipment maintenance"
2. Filter: budget > Q100,000
3. Open 3 matching tenders
4. OCR extracts technical requirements from each
5. Compare side-by-side in split view
6. Labor calculator: 2 technicians, 6 months = Q48,000
7. Export bid summary as PDF
```

### Workflow 3: Compliance Audit

```bash
1. Open awarded contract details
2. DPI/NIT validator cross-checks contractor info
3. Labor calculator verifies personnel costs match submissions
4. OCR extracts timeline commitments
5. Flag discrepancies for further investigation
```

## Target Outcomes

| User | Outcome | Metric |
|------|---------|--------|
| Contractor | Faster bid discovery | Time from tender publication to review |
| Firm | Reduced research overhead | Tenders reviewed per analyst per day |
| Auditor | Automated compliance checks | Errors flagged per audit cycle |
| Legal | Better document intelligence | Clauses reviewed per hour |
