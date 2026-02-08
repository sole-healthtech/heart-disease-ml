# Predicting Heart Disease (Synthetic Data)

## Overview
This project demonstrates a baseline machine learning workflow applied to a **synthetic healthcare dataset**.  
The goal is not clinical prediction, but to practice correct model training, validation, and evaluation while critically assessing data limitations.

This reflects the type of early modeling and judgment required before considering ML use in real healthcare workflows.

## Data
- **Source:** Kaggle Tabular Playground Series (synthetic)
- **Rows:** ~630,000
- **Features:** Demographic and clinical-style indicators
- **Target:** `Heart Disease` (Presence / Absence)

> The dataset is synthetically generated and does not represent real clinical diagnoses.  
> The target variable should be interpreted as a **proxy indicator**, not medical ground truth.

## Problem Framing
- **Task:** Binary classification  
- **y:** Presence (1) vs Absence (0) of heart-disease–like patterns  
- **X:** Feature set excluding the identifier (`id`) and target column  

The focus is on demonstrating model mechanics and evaluation discipline, not diagnostic accuracy.

## Models
Two baseline models were trained and compared:
- Decision Tree Classifier
- Random Forest Classifier

An 80/20 train–validation split was used to assess generalization to unseen data.

## Evaluation
- **Metric:** Accuracy  
- Accuracy represents the proportion of correct classifications on validation data.

While sufficient for baseline comparison, real healthcare applications would require additional metrics (e.g., sensitivity, specificity, false negatives vs false positives) to assess safety and clinical usefulness.

## Results
- Decision Tree validation accuracy: ~0.83  
- Random Forest validation accuracy: ~0.88  

The Random Forest model demonstrated improved generalization performance, consistent with ensemble methods reducing overfitting compared to a single decision tree.

## Limitations & Critical Reflection
Several limitations prevent clinical interpretation:
- Features encode complex clinical concepts (e.g., chest pain type, blood pressure, ECG changes) without context or longitudinal data.
- Measurements lack information about timing, medications, and clinical interpretation.
- Some variables are poorly defined or opaque without documentation.
- The synthetic target label does not reflect real diagnostic workflows.

As a result, **this model should not be used for clinical decision-making**. Its value lies in demonstrating technical workflow and highlighting risks of misaligned data and labels in healthcare ML.

## Takeaway
Building a technically correct model is straightforward; determining whether the data, labels, and evaluation are appropriate for real clinical use is the harder and more important challenge.

Future work would focus on clinically grounded features, longitudinal data, and evaluation metrics aligned with patient safety.

