# Aero_Sleep-AI-# Enhanced Multimodal Sleep Apnea Severity Estimator

> **Professional GitHub README Template**
>
> This document is the master documentation for the project. It explains the complete project architecture, folder structure, workflow, models, database, backend, frontend, outputs, deployment, and future scope.

---

# Table of Contents

1. Project Overview
2. Problem Statement
3. Existing System
4. Proposed System
5. Objectives
6. Features
7. End-to-End Workflow
8. Sensors Used
9. AI Models
10. Explainable AI
11. Wearer Verification
12. Folder Structure
13. Folder & File Description
14. Dataset
15. Preprocessing
16. Feature Engineering
17. Model Training
18. Backend
19. Frontend
20. Database
21. API Flow
22. Output
23. Evaluation
24. Future Scope
25. Installation
26. Repository Structure

---

# Project Overview

The Enhanced Multimodal Sleep Apnea Severity Estimator is an AI-powered healthcare solution inspired by smartwatch-based sleep monitoring. The system combines Accelerometer, Heart Rate and SpO₂ sensor signals to estimate sleep apnea severity every night instead of producing only a binary result.

The project also introduces:
- Nightly prediction
- Confidence score
- Explainable AI
- Unauthorized wearer detection
- Mobile dashboard

---

# Problem Statement

Current wearable-based sleep apnea detection mainly focuses on limited sensing and coarse predictions. Users receive delayed or binary notifications instead of detailed severity analysis.

This project addresses these limitations by combining multiple physiological signals and deep learning models.

---

# Existing System

• Motion-based detection
• Binary output
• Limited explainability
• No wearer verification
• Delayed reporting

---

# Proposed System

The proposed system collects multimodal sensor data, preprocesses it, extracts features, trains multiple AI models, compares performance, generates severity predictions, explains predictions using SHAP, verifies whether the watch is worn by the registered owner, stores reports in PostgreSQL and displays them through a Flutter application.

---

# End-to-End Workflow

Smartwatch
↓
Accelerometer + Heart Rate + SpO₂
↓
Data Collection
↓
Preprocessing
↓
Feature Engineering
↓
LSTM
↓
TCN
↓
CNN-LSTM
↓
Siamese Network
↓
SHAP Explainability
↓
Severity Prediction
↓
Database
↓
FastAPI
↓
Flutter Mobile App

---

# Sensors Used

## Accelerometer
Detects wrist movement and breathing disturbances.

## Heart Rate Sensor
Captures heart activity during sleep.

## SpO₂ Sensor
Measures blood oxygen saturation to detect oxygen desaturation events.

---

# AI Models

## LSTM
Purpose:
Sequential learning from physiological time-series.

Input:
Heart Rate, SpO₂, Accelerometer

Output:
Normal / Mild / Moderate / Severe

Files:
- model.py
- train.py
- evaluate.py
- predict.py

## TCN
Purpose:
Temporal sequence learning with convolution.

Advantages:
- Faster training
- Stable gradients
- Long sequence processing

## CNN-LSTM

Purpose:
CNN extracts local signal patterns while LSTM captures temporal dependencies.

## Siamese Neural Network

Purpose:
Verifies whether the smartwatch is worn by the registered owner.

Output:
Authorized / Unauthorized Wearer

## SHAP

Purpose:
Explains which sensor contributed most to the prediction.

---

# Folder Structure and Description

## docs/

Contains complete project documentation.

PROJECT_OVERVIEW.md
- Business problem
- Domain
- Motivation

SYSTEM_ARCHITECTURE.md
- Architecture diagrams
- Component explanation

PROJECT_WORKFLOW.md
- End-to-end execution

AI_MODELS.md
- All five model documentation

DATABASE_DESIGN.md
- ER Diagram
- Table structure

API_DOCUMENTATION.md
- REST APIs
- Request/Response examples

DEPLOYMENT_GUIDE.md
- Local deployment
- Docker
- Cloud deployment

USER_MANUAL.md
- User guide

DEVELOPER_GUIDE.md
- Developer setup

FUTURE_SCOPE.md
- Future enhancements

TROUBLESHOOTING.md
- Common issues

REFERENCES.md
- Research papers
- Dataset references

---

## dataset/

Stores all datasets.

raw/
Original downloaded datasets.

processed/
Cleaned datasets after preprocessing.

sample_data/
Small sample files for testing.

README.md
Dataset information and preprocessing notes.

---

## notebooks/

01_EDA.ipynb
Exploratory Data Analysis.

02_Preprocessing.ipynb
Cleaning and preprocessing experiments.

03_Feature_Engineering.ipynb
Feature extraction notebook.

04_Model_Training.ipynb
Training all AI models.

05_Model_Comparison.ipynb
Accuracy comparison.

06_SHAP_Analysis.ipynb
Explainability experiments.

---

## preprocessing/

data_loader.py
Loads datasets.

preprocessing.py
Handles missing values, duplicates and invalid records.

feature_engineering.py
Extracts statistical features.

normalization.py
Normalizes sensor values.

segmentation.py
Splits long recordings into windows.

signal_processing.py
Noise filtering and smoothing.

---

## models/

Each folder contains:

model.py
Defines architecture.

train.py
Training pipeline.

evaluate.py
Performance evaluation.

predict.py
Inference on new data.

saved_models/
Stores trained model weights.

---

## backend/

app.py
Application entry.

main.py
Runs FastAPI server.

routes.py
API routes.

auth.py
Authentication.

prediction.py
Prediction logic.

verification.py
Wearer verification.

database.py
Database connection.

schemas.py
Pydantic schemas.

config.py
Configuration.

utils.py
Helper functions.

---

## frontend/

Flutter application.

lib/
Application logic.

screens/
UI pages.

widgets/
Reusable UI components.

services/
API communication.

models/
Data models.

assets/
Icons and images.

---

## database/

schema.sql
Database schema.

tables.sql
Table definitions.

migration.sql
Database migration.

sample_queries.sql
Useful SQL queries.

---

## explainability/

shap_analysis.py
SHAP explanations.

feature_importance.py
Ranks features.

plots.py
Generates visualizations.

---

## outputs/

confusion_matrix/
accuracy_graph/
roc_curve/
shap_plots/
prediction_reports/
screenshots/

Stores all generated outputs.

---

## tests/

Model testing.

API testing.

Database testing.

Frontend testing.

---

# Database Tables

Users

SensorData

SleepHistory

Predictions

Alerts

WearerVerification

ModelLogs

---

# Backend Workflow

Flutter
↓

FastAPI

↓

Authentication

↓

Prediction API

↓

LSTM/TCN/CNN-LSTM

↓

Database

↓

Response

---

# Frontend Screens

• Login

• Dashboard

• Daily Report

• Weekly Report

• Monthly Report

• Prediction

• SHAP Explanation

• Alerts

• Wearer Verification

• Settings

---

# Outputs

- Sleep Apnea Severity
- Confidence Score
- SHAP Feature Importance
- Confusion Matrix
- ROC Curve
- Accuracy Graph
- Wearer Verification Result
- Historical Trend

---

# Installation

```bash
git clone <repository-url>

cd Enhanced-Multimodal-Sleep-Apnea-Severity-Estimator

pip install -r requirements.txt

uvicorn backend.main:app --reload
```

Run Flutter separately.

---

# Technologies

Python

FastAPI

Flutter

PyTorch

TensorFlow

Scikit-learn

PostgreSQL

TimescaleDB

Git

GitHub

---

# Future Scope

- ECG Integration
- Apple HealthKit Integration
- Real-time Monitoring
- Cloud Deployment
- Doctor Dashboard
- Personalized Recommendations
- Telemedicine

---

# License

MIT License
