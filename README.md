# Measuring ROI on Sponsored Search Ads: A Causal Inference Approach

Does pausing Google branded ads hurt revenue — or are you just paying for clicks you'd get for free?

This project answers that question for Bazaar.com using a **natural experiment** and **Difference-in-Differences (DiD)** methodology to separate truly incremental ad-driven traffic from organic substitution.

---

## The Business Problem

Bazaar.com's marketing team reported a **320% ROI** on Google branded sponsored ads. But this calculation assumed every sponsored click was caused by the ad — ignoring that users searching "Bazaar shoes" would likely click the free organic listing if no ad appeared.

The real question: how many of those paid clicks are actually incremental?

---

## Natural Experiment

A technical glitch turned off Google sponsored ads in weeks 10–12 of a 12-week window, while ads on Bing, Yahoo, and Ask continued running normally. This unintended interruption created a clean treatment/control setup:

- **Treated unit:** Google (ads off in weeks 10–12)
- **Control units:** Bing, Yahoo, Ask (ads on throughout)
- **Pre-period:** Weeks 1–9 | **Post-period:** Weeks 10–12

---

## Methods

- **Pre-post comparison** — baseline estimate (naive, misleading on its own)
- **Difference-in-Differences (DiD)** — accounts for market-wide growth trends using control platforms
- **Parallel trends validation** — confirmed visually in pre-period
- **DiD decomposition** — separates sponsored click loss from organic substitution gain
- **Corrected ROI calculation** — applies incremental clicks only to revenue/cost model

---

## Key Findings

| Estimate | Clicks/Week | Interpretation |
|----------|------------|----------------|
| Pre-post (naive) | -1,846 | Not significant — misleading |
| DiD (true effect) | **-9,911** | Significant at p < 0.01 |
| Sponsored clicks lost | -12,204 | Total paid clicks lost |
| Organic clicks recovered | +2,293 | ~19% cannibalization rate |

**Corrected ROI: ~580%**
Bob's 320% figure undercounts the true incremental value. Once cannibalized clicks are excluded from the cost base and only incremental clicks drive revenue, the corrected ROI nearly doubles.

---

## Recommendation

Continue the Google branded search campaign. Bob's methodology should not be used going forward. Validate the corrected estimate with a controlled geographic A/B test before scaling spend. Results apply to branded keywords only — non-branded campaigns have a different economics profile.

---

## Files

| File | Description |
|------|-------------|
| `Causal_DiD_Bazaar_Analysis.Rmd` | Full R Markdown analysis: data prep, DiD regressions, parallel trends plot, ROI calculation |
| `Causal_DiD_Analysis_Ads.pdf` | Written report with methods, findings, visualizations, and recommendations |

---

## Tools

R · tidyverse · ggplot2 · plm (panel data) · R Markdown
