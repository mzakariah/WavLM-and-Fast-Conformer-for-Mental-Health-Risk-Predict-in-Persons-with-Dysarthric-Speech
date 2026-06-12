A Multimodal AI Framework Using WavLM and Fast Conformer for Mental Health Risk Prediction and Psychological Empowerment in Persons with Dysarthric Speech
Overview

This repository contains the complete implementation, experimental protocols, preprocessing procedures, model configurations, evaluation scripts, and supplementary materials for the study:

"A Multimodal AI Framework Using WavLM and Fast Conformer for Mental Health Risk Prediction and Psychological Empowerment in Persons with Dysarthric Speech"

The framework integrates self-supervised speech representation learning, temporal sequence modeling, and socio-psychological feature fusion to simultaneously perform:

Mental Health Risk Classification
Psychological Empowerment Estimation
Cross-Dataset Generalization Analysis
Explainable Feature Importance Assessment
Repository Structure
Project/
│
├── datasets/
│   ├── UA-Speech/
│   ├── RAVDESS/
│   └── WorldBank_Disability_Data/
│
├── preprocessing/
│   ├── audio_preprocessing.py
│   ├── feature_normalization.py
│   └── psychological_indicators.py
│
├── models/
│   ├── wavlm_encoder.py
│   ├── fast_conformer.py
│   ├── fusion_module.py
│   └── multitask_head.py
│
├── training/
│   ├── train.py
│   └── validation.py
│
├── evaluation/
│   ├── metrics.py
│   ├── confusion_matrix.py
│   ├── cross_dataset.py
│   └── feature_importance.py
│
├── results/
│
├── figures/
│
└── README.md
Datasets
1. UA-Speech Database

Primary dataset used for dysarthric speech analysis.

Dataset Characteristics:

Dysarthric speech recordings
Control speech recordings
Digits
Letters
Common words
Multiple severity levels

Purpose:

Mental health risk prediction
Speech feature extraction
Temporal modeling
2. RAVDESS Dataset

Used for external validation and cross-dataset evaluation.

Contains:

Neutral
Happy
Sad
Angry
Fearful
Disgust
Calm
Surprise

Purpose:

Cross-domain validation
Generalization assessment
Emotional representation analysis
3. World Bank Disability Data

Used for Psychological Empowerment Analysis.

Indicators:

Employment Rate
Education Participation
Accessibility Index
Social Inclusion Index
Healthcare Accessibility
Assistive Technology Access
Digital Inclusion
Government Support Programs
Income Inequality
Urban-Rural Accessibility Gap

Purpose:

Psychological Empowerment Index (PEI)
Feature Importance Analysis
Data Preprocessing Protocol
Audio Processing
Step 1: Audio Loading
Sampling Rate = 16 kHz
Mono conversion
Step 2: Noise Removal
Spectral filtering
Silence removal
Step 3: Normalization
Amplitude normalization
Standard scaling
Step 4: Segmentation

Temporal Windows:

1 second
3 seconds
Full utterance
Step 5: Tokenization

Input format compatible with WavLM encoder.

Psychological Indicator Processing
Missing Values
Missing Values → Median Imputation
Scaling
Min-Max Scaling
Range = [0,1]
Correlation Screening
Threshold = |0.30|

Indicators below threshold removed.

Proposed Architecture
Stage 1: WavLM Encoder

Input:

Speech Signal

Output:

Contextual Speech Embeddings

Purpose:

Semantic understanding
Acoustic representation
Self-supervised feature extraction
Stage 2: Fast Conformer

Input:

WavLM Embeddings

Configuration:

Layers = 2
Hidden Dimension = 256
Attention Heads = 8

Purpose:

Temporal dependency modeling
Local-global context extraction
Stage 3: Socio-Psychological Fusion

Inputs:

Speech Features
+
Psychological Indicators

Fusion:

Concatenation
Dense Transformation

Output:

Multimodal Representation
Stage 4: Multi-Task Learning Head
Task A

Mental Health Risk Classification

Classes:

Control
Low
Medium
High
Very Low

Activation:

Softmax

Loss:

Cross Entropy
Task B

Psychological Empowerment Estimation

Output:

PEI Score

Loss:

Mean Squared Error
Training Configuration
Parameter	Value
Optimizer	Adam
Learning Rate	3e-5
Batch Size	32
Epochs	50
Weight Decay	1e-4
Dropout	0.30
Scheduler	Cosine Annealing
Early Stopping	Enabled
Loss Function

Total Loss:

L = λ₁Lclassification + λ₂Lregression

Where:

λ₁ = 0.7
λ₂ = 0.3
Evaluation Metrics
Classification
Accuracy
Precision
Recall
F1-Score
Specificity
ROC-AUC
Regression
MAE
RMSE
R² Score
Ablation Studies

Configurations Evaluated:

Baseline CNN
WavLM Only
WavLM + Fast Conformer
Full Proposed Framework

Metrics:

Accuracy
F1 Score
ROC-AUC
Hyperparameter Sensitivity Analysis

Evaluated Parameters:

Learning Rate
1e-5
3e-5
1e-4
Batch Size
16
32
64
Conformer Layers
1
2
4
Cross-Dataset Validation

Training Dataset:

UA-Speech

Testing Dataset:

RAVDESS

Metrics:

Accuracy
F1 Score
ROC-AUC

Purpose:

Domain generalization assessment
Temporal Stability Analysis

Speech Durations:

1 Second
3 Seconds
Full Utterance

Evaluation:

Accuracy
F1 Score
ROC-AUC

Purpose:

Robustness to varying speech lengths
Feature Importance Analysis

Method:

Random Forest Importance

Indicators Evaluated:

Employment
Accessibility
Education
Social Inclusion
Healthcare Access
Digital Inclusion
Income Inequality
Government Support

Output:

Feature Ranking
Correlation Analysis
Ethics Statement

The study utilizes publicly available and anonymized datasets, including UA-Speech, RAVDESS, and World Bank Disability Data.

No human participants were directly recruited or contacted.

Institutional Review Board (IRB) approval was therefore not required according to secondary data analysis guidelines.

Informed Consent

Informed consent was obtained by the original dataset providers during data collection.

No additional participant interaction occurred in this study.

Clinical Trial Registration

Not Applicable.

This study is a computational AI-based analysis using publicly available datasets and does not constitute a clinical trial.

Reproducibility

All preprocessing steps, hyper-parameters, model architectures, training procedures, evaluation protocols, and experimental settings are fully documented in this repository to ensure complete reproducibility.

Citation
@article{YourPaper2026,
  title={A Multimodal AI Framework Using WavLM and Fast Conformer for Mental Health Risk Prediction and Psychological Empowerment in Persons with Dysarthric Speech},
  author={Author Names},
  journal={Journal Name},
  year={2026}
}
