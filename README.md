# Multi-Omics Integrative Analysis of the ImmunoProfiler Cancer Cohort

**Author:** Jordan Dutel
**Affiliation:** Master 1 Bioinformatics – Université Claude Bernard Lyon 1
**Host Institution:** Centre Léon Bérard (CLB), Lyon, France
**Supervisor:** Dr. Youenn Drouet (Biostatistician, Data Scientist)
**Internship Period:** April 2024 – August 2024

---

## 🧬 Overview

This project was conducted during my Master 1 Bioinformatics internship at the **Centre Léon Bérard** as part of the **ImmunoProfiler** study. The goal was to perform an **integrative multi-omics analysis** to explore potential relationships between **genomic mutations**, **immune cell proportions**, and **clinical features** across multiple cancer types.

Using **genomic (SNV, CNV)**, **immunological**, and **clinical** data from nearly 500 patients of the **Profiler cohort**, this study aimed to identify molecular patterns associated with cancer subtypes and to assess whether certain biological mechanisms could be shared across tumors — in line with a **pan-cancer** perspective.

---

## ⚙️ Objectives

* Integrate **genomic**, **transcriptomic**, and **proteomic** data from the Profiler cancer cohort.
* Identify **molecular signatures** associated with clinical subtypes through **differential expression** and **pathway enrichment** analyses.
* Build **reproducible R pipelines** for preprocessing, normalization, and visualization.
* Apply **Multi-Omics Factor Analysis (MOFA)** to detect **latent factors** capturing shared and specific sources of variation across omics layers.
* Characterize **patient clusters** based on MOFA latent factors to evaluate potential biological relevance.

---

## 🧩 Dataset Description

* **Cohort:** ImmunoProfiler (subset of Profiler study, CLB)
* **Patients:** 492 total, 483 analyzed (various tumor types)
* **Data layers:**

  * *Genomic:* 92 frequently mutated cancer genes (SNV, CNV)
  * *Immunologic:* 120 immune cell populations (flow cytometry)
  * *Clinical:* Age, sex, tumor type, survival time, etc.

---

## 🧠 Methods

1. **Data Preprocessing**

   * Binary encoding of SNV/CNV data.
   * Log transformation of immunological variables for Gaussian normalization.
   * Missing data imputation handled internally by MOFA.

2. **Mutation Profiling**

   * Visualization with `GenVisR` (`waterfall()` plots).
   * Identification of gene-specific mutation patterns (e.g., *TP53*, *KRAS*, *APC*, *PIK3CA*).

3. **Integrative Multi-Omics Analysis**

   * Conducted with `MOFA2` (v1.12.1).
   * Maximum of 15 latent factors.
   * Variance partitioning between genomic and immunological layers.

4. **Clustering & Visualization**

   * Hierarchical clustering on latent factors (Ward method).
   * Dimensionality reduction with **UMAP**.
   * Cluster characterization by cancer type and omics contributions.

---

## 📈 Results Summary

* **15 latent factors** captured over **60% of total variance** across omics layers.
* **No cancer-type-specific patterns** were identified; the data suggested **shared molecular mechanisms** across tumors.
* Identified **9 patient clusters** with overlapping omics features, supporting a **pan-cancer model** of tumor biology.

---

## 🔬 Tools & Environment

| Tool / Library     | Version       | Purpose                      |
| ------------------ | ------------- | ---------------------------- |
| **RStudio**        | 2023.12.1.402 | Development environment      |
| **GenVisR**        | 1.34.0        | Mutation visualization       |
| **MOFA2**          | 1.12.1        | Multi-omics integration      |
| **UMAP / ggplot2** | latest        | Visualization and clustering |

---

## 🧭 Conclusions

This project demonstrated the potential of **multi-omics integration** to capture the complex interplay between genetic and immune features in cancer.
The absence of tumor-type-specific latent factors suggests that **molecular and immunological patterns** may be conserved across different cancer origins — reinforcing a **pan-cancer** view of tumor biology.

---

## 🚀 Future Directions

* **Survival analysis** on identified clusters (Kaplan-Meier).
* **Supervised learning (LASSO, Ridge)** to predict patient outcomes.
* **Subtype-specific MOFA models** to refine cancer-type signatures.

---

## 📚 References

Key references include:

* Argelaguet *et al.*, *Mol Syst Biol* (2018) — MOFA framework
* Hoadley *et al.*, *Cell* (2018) — Pan-cancer molecular classification
* Raufaste-Cazavieille *et al.*, *Front Mol Biosci* (2022) — Multi-omics in oncology

---

## 📂 Repository Structure

```
.
├── scripts/               # Rmd scripts for analysis (MOFA, clustering, plots)
├── results/               # Figures and model outputs
├── reports/               # Internship reports (thesis & defense)
└── README.md              # Project description
```
