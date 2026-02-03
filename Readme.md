## Problem Statement

Most ECG arrhythmia classification models:
   - Are trained and tested on a single dataset
   - Fail to generalize to real-world noisy ECGs
   - Lack explainability, making them unsuitable for clinical adoption
   - Class imbalance and improper validation strategies further reduce model reliability.

## Objectives
 - Build an ECG arrhythmia classifier with strong cross-dataset generalization
 - Evaluate performance on completely unseen datasets
 - Integrate Explainable AI (XAI) techniques to interpret predictions
 - Ensure model explanations align with cardiac physiological components

## Datasets Used

MIT-BIH Arrhythmia Database
 - Clean and curated ECG recordings
 - Used for baseline training

PhysioNet CinC 2017 Dataset
 - Noisy real-world single-lead ECG signals
 - Used for robustness validation

PTB-XL Dataset
 - Large-scale clinical 12-lead ECG dataset
 - Used for final unseen testing

## Methodology

Preprocessing 
 - Noise filtering and signal normalization
 - Patient-wise ECG segmentation

Training Strategy
 - Train on MIT-BIH + CinC 2017
 - Test on unseen PTB-XL without fine-tuning

Models Evaluated
- Classical ML: SVM, Random Forest
- Deep Learning: 1D CNN, CNN-LSTM
- Final architecture: Temporal Convolutional Network (TCN)

Explainable AI
 - Grad-CAM and SHAP used for model interpretation
 - Attribution maps aligned with P-wave, QRS complex, and RR intervals

## Evaluation Metrics

Primary Metric - Macro-F1 Score (handles class imbalance)
Secondary Metrics - Precision, Recall (Sensitivity)
Validation Strategy- 5-fold patient-wise cross-validation

