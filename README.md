<p align="center">
  <img src="figs/aidev_logo.png" alt="AIDev Logo" width="250"/>
</p>

# Analyzing Review Effort in Human vs. Agentic Pull Requests  
### A Comparative Study

[![Dataset](https://img.shields.io/badge/HuggingFace-AIDev-blue?logo=huggingface)](https://huggingface.co/datasets/hao-li/AIDev)
[![Paper](https://img.shields.io/badge/Research-Academic-green)](#)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## Author

**Mahmoud Alyosify**  
School of Computing, Queen's University  
📧 mahmoud.alyosify@queensu.ca  
Course: *CISC839 – Advanced Data Analytics*

---

## Overview

This repository presents a full analytical study on **review effort in AI-generated (agentic) vs. human-authored pull requests (PRs)** across large-scale open-source GitHub repositories.

Using a curated subset of the **AIDev dataset**, the study investigates how AI coding agents reshape review dynamics—not by reducing effort, but by **transforming its nature**.

---

## Core Insight

> Agentic pull requests do not reduce review effort—they redistribute it.  
> The challenge shifts from understanding intent to justifying trust.

---

## 📊 Dataset

- Source: [AIDev Dataset (Hugging Face)](https://huggingface.co/datasets/hao-li/AIDev)  
- Filtered subset (**>100 stars repositories**)

| Type          | PR Count |
|---------------|----------|
| Agentic PRs   | 31,284   |
| Human PRs     | 6,149    |
| **Total**     | 37,433   |

---

## 📂 Repository Structure


├── 
├── figs/ # Figures and visualizations
├── requirements.txt # Dependencies
└── README.md # Project documentation


---

## Key Findings

### peed–Quality Paradox
- Agentic PRs resolve faster (**40.4 hrs vs. 92.97 hrs**)  
- But merge less often (**76.8% vs. 82.6%**)  
Speed reflects **rejection**, not necessarily efficiency

---

### Authorship Effect
- AI authorship significantly reduces TTR  
- Suggests **reverse automation bias** (fast dismissal of AI output)

---

### Structural Drivers of Review Effort
- Review friction driven by **architectural dispersion**, not size  
- Measured via:
  - **CDI (Cognitive Dispersion Index)**
  - **RICR (Rework-to-Initial Churn Ratio)**

---

## Methodology

### 1. Data Engineering
- Construction of:
  - Time-to-Resolution (TTR)
  - CDI & RICR indices

### 2. Statistical Testing
- Welch’s t-test (unequal variance)

### 3. Regression Modeling
- OLS with HC3 robust errors  
- Isolates effect of AI authorship

### 4. GenAI-Augmented Reanalysis
- Logistic regression on merge outcomes  
- Reveals **fast-rejection dynamic**

---

## Example Outputs

### Merge Behavior
![merge](figs/pr_merge_compare_radar2.png)

### Turnaround Time Distribution
![ttr](figs/turnaround_distribution.png)

---

## Reproducibility

Install dependencies:

```bash
pip install -r requirements.txt

Dataset loads directly via Hugging Face:

hf://datasets/hao-li/AIDev/

No manual download required.

⚠️ Limitations
Observational data → unobserved confounders
TTR mixes active review with idle queue time
Organizational workflows not explicitly modeled
📄 License

MIT License
© 2026 Mahmoud Sayed Youssef

🙏 Acknowledgment

This work builds upon the AIDev dataset:

@misc{li2025aiteammates,
  title={The Rise of AI Teammates in Software Engineering (SE) 3.0},
  author={Hao Li and Haoxiang Zhang and Ahmed E. Hassan},
  year={2025},
  eprint={2507.15003},
  archivePrefix={arXiv},
  primaryClass={cs.SE}
}
