<p align="center">
  <img src="img/carbon.png" alt="Project Logo" width="100px" height="100px">
</p>

<h1 align="center">🌏 Using Machine Learning to Predict Carbon Footprint 🌱</h1>

<h3 align="center">
A data-driven approach to predicting and analyzing carbon emissions using demographic, behavioral, and environmental factors.
</h3>

<br>

<p align="center">
  <img src="img/c02_vehicle_Distance.png" alt="Carbon Emission Sample" width="70%" height="70%">
</p>

---

## 🧭 Table of Contents
1. [Introduction](#introduction)
2. [Objectives](#objectives)
3. [Dataset](#dataset)
4. [Environment Setup & Reproducibility](#environment-setup-and-reproducibility)
5. [Modeling Approach](#modeling-approach)
6. [Ablation & Error Analysis](#ablation-and-error-analysis)
7. [Results](#results)
8. [Business / Policy Impact](#business--policy-impact)
9. [Reproducibility Notes](#reproducibility-notes)
10. [Data Card](#data-card)
11. [Contact](#contact)
12. [Acknowledgments](#acknowledgments)

---

## 🧩 Introduction

This project explores **Machine Learning (ML)** methods to **predict carbon footprints** using data that represents lifestyle, demographic, and environmental behaviors.  
It demonstrates how supervised and unsupervised ML techniques can support sustainability goals by identifying high-impact factors driving carbon emissions.

The study applies **Linear Regression**, **Decision Tree**, **Random Forest**, **XGBoost**, **Support Vector Regression (SVR)**, and a **Keras Neural Network** to predict carbon emissions.  
Additionally, **KMeans** and **DBSCAN** clustering are used for unsupervised segmentation and behavioral pattern discovery.

---

## 🎯 Objectives

- Predict carbon emissions based on behavioral and environmental features.  
- Compare multiple regression and deep learning models.  
- Evaluate performance using R² and MAE metrics with confidence intervals.  
- Analyze model sensitivity (ablation) and representative failure cases.  
- Translate results into actionable sustainability recommendations.

---

## 🧾 Dataset

The dataset (`CarbonEmission.csv`) is a clean, synthetic dataset with no missing values.  
It includes variables related to **diet, transportation, waste generation, energy usage, and lifestyle habits**.

Example columns:

| Feature | Type | Description |
|----------|------|-------------|
| Diet | Categorical | Type of diet (vegan, mixed, etc.) |
| Transport | Categorical | Primary mode of transportation |
| Energy_Usage_kwh | Numeric | Monthly energy consumption (kWh) |
| Waste_Generated_kg | Numeric | Monthly solid waste (kg) |
| Renewable_pct | Numeric | % of energy from renewables |
| CarbonEmission | Numeric (Target) | Annual CO₂ emissions (kg) |

---

## ⚙️ Environment Setup and Reproducibility

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/TIWARISURAJst/Usin-ML-to-predict-Carbon-FootPrint-.git
cd Usin-ML-to-predict-Carbon-FootPrint-

---

## 🧠 Modeling Approach

This project evaluates multiple machine learning models to predict carbon emissions based on environmental and behavioral factors.  
It compares traditional regressors, ensemble methods, and neural networks.

| Category | Models Used |
|-----------|--------------|
| **Baseline Regression** | Linear Regression |
| **Tree-Based Models** | Decision Tree, Random Forest |
| **Boosting Models** | XGBoost |
| **Deep Learning** | Keras ANN (ReLU activation) |
| **Unsupervised** | KMeans, DBSCAN |

**Evaluation Metrics**
- **Mean Absolute Error (MAE)** – measures average prediction error  
- **R-squared (R²)** – measures how much variance is explained  
- **95% Confidence Intervals (via Bootstrapping)** – shows metric stability  

---

## 🔍 Ablation and Error Analysis

To test model robustness, a short ablation study was conducted by changing key hyperparameters.

| Hyperparameter | Variation | Δ MAE | Observation |
|----------------|------------|--------|--------------|
| Learning Rate | 0.001 → 0.01 | +8.3 | Overfitting observed |
| Hidden Layers | 2 → 3 | -4.5 | Slight improvement |
| Random Seed | 42 → 99 | ±2.0 | Stable performance |

**Representative Failures**
- Underprediction for users with extreme energy usage.  
- Overprediction in high renewable-energy cases.  
- Sensitivity to rare transport categories.

This analysis identifies where the models fail, which helps improve reliability in real-world deployment.

---

## 📈 Results

| Model | MAE | R² | 95% CI (MAE) | Remarks |
|--------|-----|----|---------------|----------|
| Linear Regression | 524.9 | 0.45 | (520.1 – 529.3) | Baseline |
| Random Forest | 233.8 | 0.88 | (230.2 – 236.9) | Non-linear improvement |
| XGBoost | 120.0 | 0.95 | (118.1 – 122.0) | Strong ensemble model |
| Keras ANN | 119.7 | 0.95 | (117.9 – 121.6) | Best-performing model |

<p align="center">
  <img src="img/results_plot.png" alt="Model Comparison" width="80%">
</p>

---

## 💼 Business / Policy Impact

Machine learning predictions are used to guide **real sustainability actions**:

| Stakeholder | Use Case | Potential Impact |
|--------------|-----------|------------------|
| **Hotels / Businesses** | Estimate and track carbon emissions | Reduce footprint by 15–20% |
| **Environmental NGOs** | Identify high-emission behaviors | Targeted awareness campaigns |
| **Policy Makers** | Test “what-if” carbon reduction scenarios | Evidence-based decisions |

**Example Policy Simulation**
> A 30% increase in renewable energy usage predicts an **18% reduction** in total CO₂ emissions, equivalent to **180 metric tons saved annually** for a mid-sized hotel.

---

## 🧮 Reproducibility Notes

- Random seed fixed (`random_state=42`)  
- 70:30 train-test split for all models  
- Notebooks executed sequentially  
- Models saved under `/src/models/`  
- All dependencies pinned in `requirements.txt`

---

## 📘 Data Card

| Feature | Type | Description | Missing % | Leakage Risk |
|----------|------|--------------|------------|---------------|
| Diet | Categorical | Type of diet | 0 | Low |
| Transport | Categorical | Mode of transport | 0 | Low |
| Energy_Usage_kwh | Numeric | Energy consumption | 0 | Medium |
| Waste_Generated_kg | Numeric | Waste produced | 0 | Low |
| Renewable_pct | Numeric | % renewable energy used | 0 | Low |
| CarbonEmission | Numeric (Target) | Annual CO₂ emissions | 0 | None |

🗂️ **File:** `data/data_card.csv`

---

## ✉️ Contact

**Author:** Juan Miguel López Piñero  
📧 [juanmiguelopezpinero@icloud.com](mailto:juanmiguelopezpinero@icloud.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/miguellopez19/) | [Kaggle](https://www.kaggle.com/jmlpezpinero/)

---

## 🙏 Acknowledgments

This project was developed as part of the **Machine Learning for Business Analytics (MLBA)** coursework.  
Special thanks to mentors and peers for feedback, and to open-source tools such as Scikit-learn, TensorFlow, and XGBoost for enabling reproducible research.

<p align="center">
  <img src="img/sklearn.png" width="80px" height="80px">
  <img src="img/pandas.png" width="80px" height="80px">
  <img src="img/numpy.png" width="80px" height="80px">
</p>

<p align="center">
  <em>“Data-driven sustainability — where analytics meets environmental impact.”</em>
</p>

