# Non intrusive ad click bot detection

A repository implementing methods for detecting click-fraud bots in a privacy-preserving setting, as described in the accompanying paper.

## Overview

This work focuses on identifying automated ad-clicks (bots) using only anonymized request attributes (e.g.,query strings), without relying on intrusive data collection:

1. **Exploratory Analysis**: Characterized basic features such as time‑to‑click (TTC) and query duplication patterns. We used https://github.com/wasiahmad/aol_query_log_analysis to obtain an H_0 distribution for queries in order to compute p-value  for the pair. (number_of_words , duplication count) (more details in the paper)
2. **Baseline Model**: Defined simple anomaly signals (fast TTC spikes and rare query duplicates) and optimized thresholds via grid search.
3. **Machine Learning Model**: Applied an Isolation Forest on engineered features to capture more nuanced bot behaviors.
4. **Explainability**: Derived interpretable decision‑tree rules using SHAP and UMAP embeddings to visualize anomaly clusters.
5. **Probability Calibration**: Modeled extreme Isolation‑Forest scores with a Generalized Pareto distribution to produce calibrated fraud probabilities.

## Repository Structure

```
├── datasets/                   # Sample click log data (anonymized)
├── notebook.ipynb             # Jupyter notebooks for analysis and visualization
└── README.md               # This file
```

## Installation

```bash
git clone <REPO_URL>
cd click_bot_detection
pip install -r requirements.txt
```

## Usage

1. **Exploratory Analysis**: Run `Exploratory analysis section` to reproduce basic feature plots.
2. **Baseline Classifier**: Execute `Baseline section` to compute TTC‑ and duplication‑based anomaly scores.
3. **Isolation Forest Model**: Launch `ML section (IF model fit)` to train and evaluate the Isolation Forest.
4. **Explainability & Calibration**: Use `Explainability` and `Calibration` for SHAP rule extraction and GPD fitting.

## Link to Paper

The full methodology and results are detailed in the paper: https://b7amine.github.io/2025/04/24/Non-intrusive-click-bot-detection.html
**Click-Bots Detection under Privacy Constraints** —

---

*For questions or contributions, please open an issue or submit a pull request.*
