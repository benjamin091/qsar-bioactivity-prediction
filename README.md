# QSAR Bioactivity Prediction

## Overview

This project addresses the prediction of molecular biological activity or toxicity using Quantitative Structure-Activity Relationship (QSAR) modeling. The task is to build a machine learning model that can classify molecules as active or inactive based on their chemical structure, represented by SMILES strings.

The workflow includes molecule standardization, fingerprint generation, handling missing labels, training a Random Forest model, and evaluating classification performance across multiple tasks.

## Objectives

- Load and preprocess molecular data from SMILES format.
- Convert molecules into fingerprints suitable for machine learning.
- Handle uncertain activity labels (`0`) as missing values (`NaN`).
- Perform train-test split and train a separate Random Forest classifier for each prediction task.
- Evaluate each model using confusion matrices, classification metrics, and ROC/AUC scores.
- Tune hyperparameters to improve performance.

## Workflow

1. **Data Loading**  
   - Input: SMILES strings with associated activity labels (+1 = active, -1 = inactive, 0 = unknown)  
   - Unknown labels (`0`) are treated as `NaN` and excluded from training for each task

2. **Preprocessing**  
   - Molecular standardization (if applied, done cautiously to preserve test set)  
   - Fingerprint generation using cheminformatics tools (e.g. ECFP4 or MACCS keys)  

3. **Modeling**  
   - Task-wise binary classification using Random Forest  
   - Train-test split with stratification

4. **Evaluation**  
   - Confusion matrix and classification report (precision, recall, F1-score) for each task  
   - ROC curves and AUC values  
   - Hyperparameter tuning using cross-validation or grid/randomized search  

## Technologies Used

- Python  
- scikit-learn  
- RDKit (for molecular processing and fingerprinting)  
- pandas, numpy, matplotlib, seaborn  

## Example Output

- ROC curves for each task  
- Confusion matrices with class-wise performance  
- Summary tables of tuned hyperparameters and results  


