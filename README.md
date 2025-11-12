# 🧠 Complex CVD Traits

This repository supports analyses investigating the **causal architecture, shared mechanisms, and distinct aetiology of complex and rare cardiovascular disease (CVD) traits** using Mendelian Randomisation (MR) and related causal inference methods.  

Our overarching goal is to uncover **pathophysiological pathways** underlying cardiovascular conditions through **integrative genomic and proteomic analysis**, with emphasis on instrument quality, pleiotropy-robust estimation, and biological interpretation.

---

## 🔍 Overview

This project will run **Mendelian Randomisation (MR)** analyses across six complex or rare cardiovascular phenotypes:

| Trait | Description | ICD-10 Codes / Source | Leading Publication | Self-Report Coding  |
|-------|--------------|----------------------|---------------------|---------------------|
| **Trait 1:** *Primary Pulmonary Arterial Hypertension* | Rare disease of the small pulmonary arteries, resulting in elevated pulmonary vascular resistance and right-heart failure. | **I27.0** — Primary pulmonary hypertension. <br>Source: [Epidemiology of PAH](https://onlinelibrary.wiley.com/doi/10.1177/2045894020977300) | Peacock AJ, et al. *An epidemiological study of pulmonary arterial hypertension.* **Eur Respir J** 2007; 30(1):104-9. [Link](https://publications.ersnet.org/content/erj/30/1/104) | 12 |
| **Trait 2:** *Takotsubo (Stress) Cardiomyopathy* | Also called “broken heart syndrome” — transient left ventricular dysfunction typically triggered by acute stress. | **I51.81** — Takotsubo cardiomyopathy. <br>Source: [PMCID: PMC7064300](https://pmc.ncbi.nlm.nih.gov/articles/PMC7064300/) | Aranda-Michel E, et al. *Takotsubo Cardiomyopathy: Associations and Risk Factors.* Continental Mid-America & Mountain Healthcare Conf 2024. [Link](https://scholarlycommons.hcahealthcare.com/cgi/viewcontent.cgi?article=1002&context=continental-midamerica-mountain2024) | No dedicated code. |
| **Trait 3:** *Isolated Myocarditis* | Inflammation of the myocardium (heart muscle) not secondary to another specified condition. | **I40.1** — Isolated myocarditis. <br>Source: [AAPC ICD-10](https://www.aapc.com/codes/icd-10-codes/I40.1) Note needs to be dropped from analysis due to minimal case numbers. | Li C, et al. *Global, regional, and national epidemiology of myocarditis and inflammatory cardiomyopathy.* **Heart BMJ** 2025; 111:867-876. [Link](https://heart.bmj.com/content/111/18/867) | No dedicated code. |
| **Trait 4:** *Secondary Pulmonary Arterial Hypertension* | Pulmonary arterial hypertension due to an identifiable cause (e.g., connective tissue disease, drugs, congenital heart disease) rather than idiopathic. | **I27.21** — Secondary pulmonary arterial hypertension (nt. 127.2 in UKB). <br>Source: [ICD10data](https://www.icd10data.com/ICD10CM/Codes/I00-I99/I26-I28/I27-/I27.21) | George MG, et al. *Pulmonary Hypertension Surveillance — United States, 2001–2010.* **CHEST J** 2014. [Link](https://journal.chestnet.org/article/S0012-3692%2815%2948835-X/fulltext) | 45 |
| **Trait 5:** *Brugada Syndrome* | A genetic arrhythmia syndrome characterised by ST-segment elevation in right precordial leads and high risk of ventricular fibrillation/sudden death in structurally normal hearts. | **I49.8** — Other specified cardiac arrhythmias (used to capture Brugada syndrome). <br>Source: [ICD Codes AI](https://icdcodes.ai/diagnosis/brugada-syndrome/documentation) | El Sayed M. *Brugada Syndrome.* **StatPearls** 2023. [Link](https://www.ncbi.nlm.nih.gov/books/NBK519568/) | No dedicated code. |

Each trait will be analysed using harmonised genetic instruments derived from proteomic, transcriptomic, and GWAS resources.

---

## 🧬 Aims

1. **Identify causal protein–trait relationships** that inform CVD aetiology.  
2. **Characterise pleiotropic architecture** across complex and rare CVD endpoints.  
3. **Compare estimator behaviour** across MR methods (e.g. IVW, MR-Egger, GSMR, RAPS, GENIUS-MAWII).  
4. **Integrate tissue-specific signals** to explore site-specific effects (e.g. plasma vs PBMC).  
5. **Prioritise translational targets** based on instrument strength and biological plausibility.  

---

## 📂 Repository Structure

```
complex-cvd-traits/
│
├── data/                        # Core datasets and processed inputs
│   ├── raw/                     # Unmodified data sources (protected)
│   ├── processed/               # Cleaned, harmonised datasets
│   ├── instruments/             # Exposure SNP lists and harmonised instruments
│   └── outcomes/                # Summary stats for each of the six traits
│
├── users/                       # User-specific working directories
│   ├── coldnall/
│   └── ielliott/
│
├── scripts/                     # Analysis scripts and pipelines
│   ├── MR/                      # Core MR workflows
│   ├── QC/                      # QC, harmonisation, and instrument checks
│   ├── visualisation/           # Forest plots, scatter plots, etc.
│   └── utils/                   # Helper functions and shared modules
│
├── results/                     # Output folders per trait and method
│   ├── <trait_name>/
│   └── summary_tables/
│
├── logs/                        # Job submission and runtime logs
│
├── docs/                        # Documentation, figures, and reports
│   ├── methods/
│   └── interpretation_notes/
│
└── README.md
```

---

## 🧩 Methods (Outline)

Each trait analysis will follow the same pipeline:

1. **Instrument Selection:**  
   Filter genome-wide significant variants, LD-clump, and harmonise alleles.  

2. **Exposure–Outcome Harmonisation:**  
   Match SNPs between protein (or other exposure) datasets and the outcome GWAS.  

3. **MR Estimation:**  
   Apply multiple estimators (IVW, Egger, Weighted Median, GSMR, RAPS, GENIUS-MAWII).  

4. **Diagnostics & Sensitivity:**  
   Evaluate heterogeneity, leave-one-out stability, and pleiotropy robustness.  

5. **Visualisation & Reporting:**  
   Generate summary tables, forest plots, and interactive dashboards where applicable.  

---

## 🧭 Collaboration and Usage

Each user should work within their own folder under `users/`, following naming conventions:  

```
users/<firstname_surname>/
```

Intermediate outputs (temporary results, personal notes, draft plots) should remain there until validated and ready for promotion to shared `/results/` or `/docs/` directories.

---

## 🧾 Citation & Acknowledgements

If using this repository or associated results, please cite:

> *Causal inference across rare and complex cardiovascular phenotypes using proteomic and genetic instruments (2025).*

---

## 📅 Project Status

| Stage | Description | Expected Completion |
|-------|--------------|--------------------|
| Data collation | Gathering exposure/outcome datasets | ☐ *Pending* |
| Instrument harmonisation | SNP matching and QC | ☐ *In progress* |
| MR estimation | Multi-method causal analysis | ☐ *Planned* |
| Sensitivity and visualisation | Diagnostics and reporting | ☐ *Planned* |
| Manuscript preparation | Results synthesis and drafting | ☐ *Planned* |
