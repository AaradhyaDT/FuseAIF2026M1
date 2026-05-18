# FuseAIF_WK4_LinearModels

## Overview
This repository contains the Week 4 Linear Models assignment for the Fuse AI Fellowship. The task focuses on Telco customer churn prediction using linear classification methods, including:
- data inspection and cleaning
- feature engineering and preprocessing
- logistic regression and linear classifier baselines
- model evaluation with accuracy, precision, recall, F1, ROC-AUC, and PR-AUC
- threshold-based decision analysis for business constraints

## Files
- `W4_Linear_Models_Assignment.ipynb` — main notebook with code, exploration, models, and interpretations
- `W4_Task_Plan.md` — assignment task plan and instructions
- `W4_Linear_Model_Assignment.pdf` — PDF version of the notebook or assignment deliverable
- `W4 Linear Model Assignment Overview.pdf` — assignment overview and dataset description
- `README.md` — project summary

## Dataset
The notebook uses the Telco Customer Churn dataset and performs:
- type correction for `TotalCharges`
- handling of whitespace nulls
- categorical encoding for service and demographic features
- target encoding for churn labels

## How to run
1. Open `W4_Linear_Models_Assignment.ipynb` in Jupyter or VS Code Notebook.
2. Run the cells sequentially from the setup section through the classification experiment.
3. Review the markdown notes after each block for interpretation and findings.

## Goal
Build an interpretable linear-model pipeline for churn classification while highlighting the impact of data quality, class imbalance, and business-aware decision thresholds.
