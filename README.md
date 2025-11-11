# 🧠 Complex CVD Traits

This repository supports analyses investigating the **causal architecture, shared mechanisms, and distinct aetiology of complex and rare cardiovascular disease (CVD) traits** using Mendelian Randomisation (MR) and related causal inference methods.  

Our overarching goal is to uncover **pathophysiological pathways** underlying cardiovascular conditions through **integrative genomic and proteomic analysis**, with emphasis on instrument quality, pleiotropy-robust estimation, and biological interpretation.

---

## 🔍 Overview

This project will run **Mendelian Randomisation (MR)** analyses across six complex or rare cardiovascular phenotypes:

| Trait | Description | ICD-10 Codes / Source | Notes |
|-------|--------------|----------------------|-------|
| **Trait 1:** *[placeholder — e.g., Coronary Artery Disease]* |  |  |  |
| **Trait 2:** *[placeholder — e.g., Atrial Fibrillation]* |  |  |  |
| **Trait 3:** *[placeholder — e.g., Heart Failure]* |  |  |  |
| **Trait 4:** *[placeholder — e.g., Hypertrophic Cardiomyopathy]* |  |  |  |
| **Trait 5:** *[placeholder — e.g., Peripheral Artery Disease]* |  |  |  |
| **Trait 6:** *[placeholder — e.g., Pulmonary Hypertension]* |  |  |  |

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

## ⚙️ Suggested Additions

- **`envs/`** — YAML or `.txt` files specifying reproducible Conda/Mamba environments for HPC use.  
- **`notebooks/`** — Jupyter notebooks for exploratory or visual work.  
- **`jobs/`** — Cluster submission scripts (SGE/SLURM), with standard logging and job arrays.  
- **`meta/`** — Metadata tables linking exposure/outcome datasets, trait mappings, and analysis provenance.  

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

This work is part of the **Complex CVD Traits** research stream at the *University of Edinburgh / Complex Disease Modelling Group*.

If using this repository or associated results, please cite:

> *Complex CVD Traits Consortium (2025). Causal inference across rare and complex cardiovascular phenotypes using proteomic and genetic instruments.*

---

## 📅 Project Status

| Stage | Description | Expected Completion |
|-------|--------------|--------------------|
| Data collation | Gathering exposure/outcome datasets | ☐ *Pending* |
| Instrument harmonisation | SNP matching and QC | ☐ *In progress* |
| MR estimation | Multi-method causal analysis | ☐ *Planned* |
| Sensitivity and visualisation | Diagnostics and reporting | ☐ *Planned* |
| Manuscript preparation | Results synthesis and drafting | ☐ *Planned* |
