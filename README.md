# NZ Jobs Market: AI Exposure Visualizer

A D3.js-based treemap visualization showing AI exposure across 50+ New Zealand occupations.

**Live Demo:** Open `index.html` in a modern web browser.

---

## 📊 What This Shows

This prototype visualizes the **AI exposure** of New Zealand occupations on a scale of 0-10, where:

- **0-3 (Green)**: Low exposure — physical, hands-on work difficult to automate
- **4-5 (Orange)**: Moderate exposure — mix of physical and digital work  
- **6-7 (Orange-Red)**: High exposure — largely digital/screen-based work
- **8-10 (Red)**: Very high exposure — routine digital tasks, easy to automate

**Rectangle size** = number of people employed in that occupation (larger rectangles = more employment)

---

## 🎯 Scoring Methodology

Scoring is based on **Andrej Karpathy's AI Jobs framework** (https://github.com/karpathy/jobs), adapted for New Zealand context.

### Key Criteria:
1. **How digital is the output?** Pure screen-based work scores higher.
2. **Does it require in-person presence?** Physical work requiring on-site presence scores lower.
3. **How routine vs. creative?** Highly routine digital tasks score highest.
4. **Does it require human relationships?** Care work, teaching, counseling require human connection — limits automation.
5. **NZ-specific factors:** Remote work adoption, digital maturity, industry structure.

### Sample Scores:

| Occupation | Score | Reason |
|---|---|---|
| Software Developer | 8 | Almost entirely screen-based; AI co-pilots assist with coding |
| Data Entry Operator | 10 | Routine digital work; easily automated by OCR/RPA |
| Accountant | 7 | Spreadsheets and digital records; routine reconciliation automatable |
| Teacher | 6 | Mix of digital lesson planning and human interaction |
| Nurse | 5 | Physical patient care essential; some digital charting |
| Electrician | 3 | Hands-on work in physical environments; decision-making on-site |
| Firefighter | 1 | Extremely dangerous, unpredictable physical work |

---

## 📁 Files

- **`index.html`** — Interactive visualization (open this in your browser)
- **`data.json`** — NZ occupation data with AI exposure scores
- **`nz-occupations.json`** — Base data (50+ occupations, employment, wages)
- **`score_ai_exposure.py`** / **`score_ai_exposure.js`** — Scripts to score occupations using Claude API
- **`README.md`** — This file

---

## 🎨 Features

### Interactive Controls

- **Color by:** Toggle between AI Exposure Score, Growth Outlook, or Median Wage
- **Sort by:** Order occupations by Employment Size, AI Exposure, or Wage
- **Search:** Filter occupations (e.g., "Software", "Nurse", "Teacher")
- **Hover:** See full details including AI exposure reasoning
- **Reset:** Clear filters and return to full view

### Statistics Dashboard

- **Total Employment Covered** — ~1.5M people represented
- **Average AI Exposure** — Weighted average across all visible occupations
- **Occupations Analyzed** — Number of job categories included
- **High Risk Count** — How many occupations score 8-10 for AI exposure

---

## 📊 Data Sources

Data compiled from:

1. **Stats NZ Labour Market Statistics** (December 2024 Quarter)
   - Employment figures by broad occupation groups
   - Median weekly earnings by occupation
   - Growth outlook (strong, moderate, stable, decline)
   - Source: https://www.stats.govt.nz/information-releases/labour-market-statistics-december-2024-quarter/

2. **AI Exposure Scoring**
   - Adapted from Andrej Karpathy's Jobs project (https://github.com/karpathy/jobs)
   - Assessed using Claude 3.5 Sonnet with domain-specific rubric
   - Focused on NZ labor market context

---

## 🔧 How to Update Data

### Add/Remove Occupations

Edit `nz-occupations.json`:

```json
{
  "id": "category-001",
  "name": "Occupation Name",
  "employment": 15000,
  "median_wage_weekly": 1350,
  "growth_outlook": "strong",  // strong | moderate | stable | decline
  "description": "What the job involves..."
}
```

Then re-run scoring (requires Anthropic API key):

```bash
node score_ai_exposure.js   # or: python3 score_ai_exposure.py
```

### Update AI Exposure Scores

Manually edit `data.json`:

```json
{
  ...
  "ai_exposure_score": 7,
  "ai_exposure_reasoning": "Mostly digital work..."
}
```

Refresh the browser to see changes (F5).

---

## 🤖 Scoring Pipeline (Advanced)

To re-score all occupations using Claude API:

```bash
# Set API key
export ANTHROPIC_API_KEY="sk-..."

# Run scoring (Node.js version)
node score_ai_exposure.js

# Or Python version (requires anthropic package)
python3 -m pip install anthropic
python3 score_ai_exposure.py
```

**Note:** This will call Claude API multiple times (once per occupation). Costs ~$0.50-1.00 for full dataset.

---

## 📈 Key Insights

Based on current data (50+ NZ occupations):

### Most Exposed to AI Risk (Score 8-10)
- Data Entry Operators (10) — Routine data tasks
- Secretaries/Receptionists (8) — Automated scheduling, chatbots
- Bookkeepers (8) — Automatable transaction recording
- Legal Professionals (8) — Contract review, legal research
- Software Developers (8) — AI co-pilots assisting coding

### Safest from AI (Score 0-3)
- Firefighters (1) — Unpredictable, dangerous, requires presence
- Cleaners (1) — Physical manual work
- General Labourers (1) — Unpredictable environments
- Welders (2) — Skilled manual metalwork
- Plumbers (2) — On-site problem-solving

### Moderate Risk (Score 4-5)
- Nurses (5) — Physical care essential + digital charting
- Teachers (6) — Mix of digital planning + human interaction
- Sales Reps (6) — CRM tools + relationship-based

---

## 🎓 Context: For Spark NZ People & Culture Team

This visualization is designed to:

1. **Demonstrate AI exposure trends** across the NZ labour market
2. **Identify which occupations/roles** are most at risk of disruption
3. **Support conversations** about workforce planning and upskilling
4. **Inform talent strategy** — where to invest in development
5. **Provide data-driven talking points** for leadership discussions

### Discussion Questions:
- Which roles in our organization align with high-exposure occupations?
- What upskilling or reskilling is needed for teams in high-exposure roles?
- How can we position Spark to benefit from these changes?
- Which emerging skills should we prioritize in hiring/development?

---

## 📚 References

- **Karpathy's Jobs Project**: https://github.com/karpathy/jobs
- **Stats NZ Labour Statistics**: https://www.stats.govt.nz/topics/labour-market/
- **ANZSCO Occupational Classification**: https://www.abs.gov.au/ausstats/abs@.nsf/mf/1220.0
- **Anthropic Claude API**: https://docs.anthropic.com/

---

## 🚧 Future Enhancements

- [ ] Geographic breakdown (Auckland, Wellington, Christchurch)
- [ ] Industry sector view (Tech, Healthcare, Retail, etc.)
- [ ] Salary bands and income distribution
- [ ] Skills mapping — which skills are at risk?
- [ ] Interactive "What if?" scenarios
- [ ] Export to PDF for presentations
- [ ] API for integration with HR systems

---

## 📝 License

This prototype is provided as-is for internal use at Spark NZ.

Based on Andrej Karpathy's open-source Jobs project.

---

## 💬 Questions?

For questions about the visualization or methodology, refer to:
- This README
- `data.json` schema and reasoning fields
- Karpathy's original methodology: https://github.com/karpathy/jobs

**Last Updated:** March 2026  
**Data Source:** Stats NZ December 2024 Quarter
