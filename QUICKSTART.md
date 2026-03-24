# 🚀 Quick Start Guide

## Open the Visualizer

```bash
# Option 1: Direct open (macOS/Linux)
open ~/openclaw-nz-jobs/index.html

# Option 2: Serve locally (any OS)
cd ~/openclaw-nz-jobs
python3 -m http.server 8000
# Then visit: http://localhost:8000
```

That's it! You should see an interactive treemap with 57 NZ occupations.

---

## What You're Looking At

### The Visualization
- **Each rectangle** = one occupation
- **Size of rectangle** = how many people work in that job (bigger = more people)
- **Color** = AI exposure risk:
  - 🟢 **Green** = Safe (0-3) — physical hands-on work
  - 🟠 **Orange** = Moderate (4-5) — mixed work
  - 🔴 **Red** = High Risk (8-10) — digital screen-based work

### Quick Stats (Bottom)
- **Total Employment:** ~1.8 million NZ jobs covered
- **Average AI Exposure:** 4.8/10 (moderate overall risk)
- **Occupations:** 57 analyzed
- **High Risk:** 6 occupations scoring 8-10 (mostly data/clerical roles)

---

## Interact

1. **Hover** over any rectangle to see:
   - Employment count
   - Median weekly wage
   - AI exposure score (0-10)
   - Why it scores that way

2. **Search** to filter occupations:
   - Type "Software" → see all tech roles
   - Type "Nurse" → see healthcare roles
   - Type "Manager" → see management roles

3. **Change colors:**
   - "AI Exposure" (default) — red = risky
   - "Growth Outlook" — shows job market trends
   - "Wage" — shows salary distribution

4. **Click Reset** to go back to full view

---

## Key Findings

### Most at Risk from AI 🔴
1. **Data Entry Operators** (10/10) — Routine digital tasks
2. **Secretaries/Receptionists** (8/10) — Phone/email automation
3. **Bookkeepers** (8/10) — Automatable accounting
4. **Legal Professionals** (8/10) — AI assists contract review
5. **Data Analysts** (8/10) — AI does the analysis

### Safest from AI 🟢
1. **Firefighters** (1/10) — Unpredictable, dangerous
2. **Cleaners** (1/10) — Physical manual work
3. **Plumbers, Electricians** (2-3/10) — Hands-on trades
4. **Care Workers** (2/10) — Human interaction essential

### Moderate Risk 🟠
- **Nurses, Teachers** (5-6/10) — Mix of human interaction + digital tools
- **Managers** (6-7/10) — Mostly meetings, email, digital planning

---

## Use This For

✅ **Board/Leadership Conversations**
- "Here's where the NZ job market faces AI disruption"
- Share specific occupation scores relevant to Spark

✅ **Talent Strategy**
- Which roles need upskilling?
- Where should we invest in development?
- Which emerging skills to prioritize?

✅ **Departmental Discussions**
- "Your role scores 7/10 for AI exposure — here's what that means"
- "Here's the industry context"

✅ **Hiring/Recruitment**
- Identify future-proof roles
- Plan for skills development

---

## Customize It

### Add Your Own Data
Edit `nz-occupations.json` to add company-specific roles or more occupations.

### Update AI Scores
Edit `data.json` and change `ai_exposure_score` and `ai_exposure_reasoning`.

### Change Colors
Edit the HTML color scheme or create custom scales.

**Note:** All changes reflected instantly when you refresh the browser.

---

## Questions?

- **What's "AI exposure"?** How much of a job is digital/screen-based and routine (i.e., replaceable by AI)
- **Why is Software Dev 8/10 not 10/10?** Because architecture, design decisions, and human judgment still matter — AI assists but doesn't replace
- **Why is Nurse only 5/10?** Physical patient care is essential and requires human presence; some charting becomes digital
- **Is this accurate?** This is a prototype based on Stats NZ data + domain reasoning. Real risk varies by company, team, individual skills

For full methodology, see **README.md**.

---

## Share It

- **Export:** Print/screenshot for presentations
- **Share link:** Send this folder to colleagues
- **Embed:** HTML/D3.js code can be embedded in web apps

---

**Ready to explore?** Open `index.html` now! 🎯
