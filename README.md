# Analyzing Review Effort in Human vs. Agentic Pull Requests  
### A Comparative Study

**Author:** Mahmoud Alyosify  
**Institution:** School of Computing, Queen's University  
**Course:** CISC839 – Advanced Data Analytics  
**Contact:** mahmoud.alyosify@queensu.ca  

---

## Abstract

This repository contains the full replication package and analytical pipeline for studying review effort in AI-generated (*agentic*) versus human-authored pull requests (PRs) across large-scale open-source GitHub repositories.

Using a curated dataset of **37,433 PRs**, the analysis evaluates **Time-to-Resolution (TTR)** and **Merge Rate** as primary metrics. To further diagnose review friction, the study introduces two novel metrics:

- **Cognitive Dispersion Index (CDI)**
- **Rework-to-Initial Churn Ratio (RICR)**

Findings reveal a **speed–quality paradox**, showing that agentic PRs transform—rather than reduce—review effort.

---

## Repository Contents

- `notebook_A1_CISC839_Alyosify_Mahmoud.ipynb`  
  End-to-end pipeline: data engineering, EDA, hypothesis testing, and regression modeling.

- `AI_Prompts_Alyosify_Mahmoud.xlsx`  
  Documentation of GenAI prompts used during methodological reanalysis.

- `Report.pdf`  
  Final academic report detailing methodology, findings, and limitations.

---

## Dataset Details

The analysis is based on a filtered subset of the **AIDev dataset**, constrained as follows:

- **Repositories:** 2,807 repositories with >100 GitHub stars  
- **Agentic PRs:** 31,284 (e.g., Codex, Copilot, Devin, Cursor, Claude Code)  
- **Human PRs:** 6,149 (matched to the same repository distribution)

---

## Key Findings

- **Speed–Quality Paradox:**  
  Agentic PRs resolve faster (mean TTR ≈ 40.4 hrs vs. 92.97 hrs) but have a lower merge rate (76.8% vs. 82.6%), suggesting faster rejection rather than smoother approval.

- **Authorship Effect:**  
  AI-authored PRs significantly reduce resolution time, potentially reflecting *reverse automation bias*—rapid dismissal without deep review.

- **Structural Drivers of Friction:**  
  CDI–RICR analysis shows that **architectural dispersion**, not PR size, drives rework and review difficulty.

---

## Methodology

The analytical pipeline includes:

- **Data Engineering:**  
  Metric standardization and construction of TTR, CDI, and RICR.

- **Statistical Testing:**  
  Welch’s t-test for comparing mean TTR across cohorts.

- **Regression Modeling:**  
  OLS with HC3 robust standard errors to isolate authorship effects.

- **GenAI-Augmented Reanalysis:**  
  Logistic regression on merge outcomes, revealing the *fast-rejection dynamic*.

---

## Reproducibility

Install required dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy statsmodels scikit-learn pyarrow
````

* Dataset is loaded directly via Hugging Face:

  ```
  hf://datasets/hao-li/AIDev/
  ```
* No manual download required.

---

## 📄 License

MIT License
© 2026 Mahmoud Sayed Youssef
🔥
```
