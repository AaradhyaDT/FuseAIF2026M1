# 🎓 Fuse AI Fellowship 2026 — Phase 2 Consolidated Portfolio
**Phase 2 · Deliverables Portfolio · Week 1 – 4 Projects**

Welcome to the consolidated portfolio workspace for the Fuse AI Fellowship 2026 (Phase 2). This workspace contains the complete, validated, and highly documented implementations across Module 1, specializing in core Statistical Machine Learning foundations, Production-Grade Agentic pipelines, and Linear Model diagnostics.

---

## 🗺️ Module 1 Workspace Map

This repository houses four primary weekly deliverables, ordered by technical progression:

### 📂 [WK1 — ML Core Concepts](WK1/)
* **Focus:** Deep mathematical foundations of machine learning, linear algebra, vector spaces, and standard distance metric optimization.
* **Core Assets:** Computational notebooks demonstrating vector operations, eigenvalues, projections, and metrics derivations.

### 📂 [WK2 — Exploratory Data Analysis & Supervised Learning](WK2/)
* **Focus:** Advanced exploratory data analysis, visual diagnostics, handling missing values, standard feature encoding, and initial tree-based vs. distance-based classifier comparisons.
* **Core Assets:** Structured visualization folders, feature-importance correlation heatmaps, and initial evaluation tables.

### 📂 [WK3 — Production Text-to-SQL Pipeline](WK3/fuseAiF_wk3_text2sql/)
* **Focus:** An enterprise-grade, agentic pipeline converting natural language queries into accurate SQL statements, running database queries, and validating outputs.
* **Key Components:**
  - 🧠 **[main.py](WK3/fuseAiF_wk3_text2sql/main.py):** Main orchestration agent driving natural language interpretation.
  - 🛠️ **[sql_generator.py](WK3/fuseAiF_wk3_text2sql/sql_generator.py):** Query schema compiler and dynamic prompt manager.
  - 🔄 **[executor.py](WK3/fuseAiF_wk3_text2sql/executor.py):** Secure SQL sandbox running queries against [seed.sql](WK3/fuseAiF_wk3_text2sql/seed.sql).
  - 🛡️ **[validator.py](WK3/fuseAiF_wk3_text2sql/validator.py):** Output schema inspector and query sanity validator.
  - 📈 **[run_benchmark.py](WK3/fuseAiF_wk3_text2sql/run_benchmark.py):** Robust performance testing and query coverage metrics.
  - 🌐 **[streamlit_app.py](WK3/fuseAiF_wk3_text2sql/streamlit_app.py):** Interactive, responsive user interface.

### 📂 [WK4 — Linear Models & Business Diagnostics](WK4/)
* **Focus:** Rigorous, end-to-end executed machine learning pipeline modeling customer churn and Customer Lifetime Value (CLV) on the Telco dataset.
* **Key Highlights:**
  - 📓 **[W4_Linear_Models_Assignment_executed.html](WK4/W4_Linear_Models_Assignment_executed.html):** Fully rendered, production-grade review document.
  - 🏆 **Classification Pipeline:** Calibrated L-BFGS Logistic Regression utilizing a budget-constrained decision threshold of `0.385` to maximize top calling funnel precision.
  - 📉 **Tenure Regression & CLV:** Ridge Regression tenure model (test $R^2 = 0.548$) mapped into continuous `CLV = MonthlyCharges * tenure` to support value-weighted business sorting.
  - 🛡️ **Evaluation & Target Leakage:** Stratified 5-Fold Cross-Validation, convergence learning curves, and a deliberate data-leakage simulation demonstrating structural validation blindspots.
  - 📊 **Tracker:** [progress.md](WK4/progress.md) mapping 100% completed status across all 19 sub-tasks.

---

## 🌐 3. Interactive Codebase Knowledge Graph (Graphify)

To ensure high modularity and clean architectural abstraction, the entire workspace is integrated into a unified semantic codebase graph in [graphify-out/](graphify-out/). The compiled graph catalogs dependencies, call structures, data flows, and documentation maps across all four weekly directories.

### 📊 Graph Statistics:
- **Total Nodes:** 1,350 structural AST blocks
- **Total Edges:** 1,387 semantic relationships
- **Total Communities:** 185 logical code clusters

### 🗺️ Visualizing the Graph Locally:
You can host and navigate the interactive, rich-visual Vis.js codebase map in your browser:
```powershell
# Serve the compiled knowledge graph from the root workspace
python -m http.server 8080 --directory graphify-out
```
*Once running, navigate to `http://localhost:8080/graph.html` in your web browser to visually explore the interactive code community structures!*

---

## ⚙️ Central Environment Setup

All weekly assignments share a highly optimized virtual environment structure.

### 1. Initialize Python Environment
To install core libraries (`pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`, `jupyter`, `streamlit`, `papermill`, `nbconvert`):
```powershell
# Create a virtual environment at the root or within specific weekly folders
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# Upgrade pip and install standard configurations
pip install --upgrade pip
pip install -r WK3/fuseAiF_wk3_text2sql/requirements.txt
```

### 2. Verify Graph Integrity
Re-run the codebase AST extractor at any time to keep the semantic maps fully synchronized with code modifications:
```powershell
graphify update .
```