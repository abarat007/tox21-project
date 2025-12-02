# Single-Task Molecular Toxicity Prediction on Tox21 (SR-p53)

This repo contains the code, notebook, and results for my **CMPB 5002 final project**, where I train and evaluate machine learning models to predict **SR-p53 toxicity** on the **Tox21** benchmark dataset.

The project focuses on a **single binary endpoint (SR-p53)** and compares a simple baseline model against a graph-based neural network, with hyperparameter sweeps and result visualizations.

---

## Project Overview

- **Task:** Binary classification of SR-p53 activity (active vs. inactive).
- **Dataset:** Tox21 (filtered to non-missing SR-p53 labels + valid SMILES).
  - Final dataset: **6,767 molecules**
  - **423** positives (SR-p53-active)  
  - **6,344** negatives  
  - Positive rate ≈ **6.3%**
- **Models:**
  - **Baseline:** Logistic Regression on Morgan fingerprints
  - **GNN:** Single-task GNN trained on molecular graphs (SR-p53 only)
- **Metrics:** AUROC, AUPRC, accuracy, F1-score

---

## Key Files

- `*.ipynb` – Main Jupyter notebook with the full experimental pipeline:
  - data loading & preprocessing  
  - model training (baseline + GNN)  
  - hyperparameter sweeps  
  - plots and tables for the report
- `tox21.csv` – Tox21 dataset file used for this project.
- `tox21_SR-p53_gnn_depth_sweep.csv` – Results of the **GNN depth (n_layers)** sweep.
- `tox21_SR-p53_gnn_dropout_sweep.csv` – Results of the **GNN dropout** sweep.
- `tox21_SR-p53_baseline_vs_gnn.csv` – Test-set comparison of **baseline vs. best GNN**.

(If your repo has a different layout, adjust the filenames/paths accordingly.)

---

## Setup

You can run everything either locally or in Google Colab.

**Dependencies (core):**

- Python 3.x  
- `deepchem`  
- `rdkit-pypi`  
- `numpy`, `pandas`, `scikit-learn`  
- `matplotlib`, `seaborn`  
- (plus any GNN / torch dependencies used in the notebook)