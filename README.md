# 🩺 Chronic Kidney Disease (CKD) Classification Model

> A machine learning project using anonymized blood sample data to classify and predict Chronic Kidney Disease across different age groups and medical aid membership bands — sourced from a private hospital in Krugersdorp, South Africa.

---

## 📌 Table of Contents

- [Project Overview](#project-overview)
- [Background & Motivation](#background--motivation)
- [Dataset Description](#dataset-description)
- [Project Structure](#project-structure)
- [Notebook Walkthrough](#notebook-walkthrough)
- [Tech Stack & Dependencies](#tech-stack--dependencies)
- [Getting Started](#getting-started)
- [Model Summary](#model-summary)
- [Results & Evaluation](#results--evaluation)
- [Ethical Considerations](#ethical-considerations)
- [Acknowledgements](#acknowledgements)
- [License](#license)

---

## 📖 Project Overview

This project applies supervised machine learning to classify patients as having Chronic Kidney Disease (CKD) or not, based on anonymized blood sample data. The goal is to assist medical researchers and healthcare practitioners in identifying CKD patterns early across different demographic segments — particularly age groups and medical aid membership bands.

The model was developed as part of a support effort for a master's research project focused on chronic disease analysis within a South African community healthcare context.

---

## 🌍 Background & Motivation

Chronic Kidney Disease is a progressive condition that often goes undiagnosed until it reaches advanced stages. In South African communities, access to timely diagnostics is limited, making predictive modelling a valuable supplement to clinical practice.

This dataset was sourced through a collaboration with a medical staff member at a private hospital in **Krugersdorp**, who required data science support for their research. As someone embedded in both the local community and the Data Science & AI space, this project presented a meaningful opportunity to:

- Apply machine learning to a real-world healthcare problem
- Support academic research with practical tooling
- Demonstrate responsible and ethical use of patient data

---

## 📊 Dataset Description

| Property | Detail |
|---|---|
| **Source** | Private hospital, Krugersdorp, South Africa |
| **Collection Method** | Blood sample analysis |
| **Anonymization** | Full — all PII removed (patient IDs, names, ID numbers, addresses, medical aid details) |
| **Segmentation** | Age groups & medical aid membership bands |
| **Target Variable** | CKD Class (positive / negative) |

> ⚠️ **Note:** The raw dataset is not included in this repository in compliance with the data privacy agreement under which it was shared. All analysis is performed on the anonymized version only.

### Key Features (Blood Markers & Clinical Indicators)

The dataset includes a combination of clinical and demographic features. Common blood-based CKD indicators used in the model include:

- Serum Creatinine
- Blood Urea Nitrogen (BUN)
- Glomerular Filtration Rate (GFR / eGFR)
- Haemoglobin levels
- Sodium, Potassium, and other electrolytes
- Blood Pressure readings
- Albumin / Protein levels
- Age group band
- Medical aid membership tier

> Feature names may differ slightly depending on how they appear in the notebook — refer to the data exploration section for exact column names.

---

## 🗂️ Project Structure

```
Chronic_Kidney_Disease_Class/
│
├── README.md                   # Project documentation (you are here)
├── CKD_Observation.ipynb    # Main Jupyter Notebook
├── requirements.txt            # Python dependencies
├── CKD_Dataset/
│   └── ckd.csv      # Anonymized dataset
├── mlruns/
│   └── Experiment_ID
│   └── models
├── mlaftifacts/
│   └── Experiemtn_ID
│   └── models
```

---

## 📓 Notebook Walkthrough

The main notebook `CKD_Observation.ipynb` is structured into the following sections:

### 1. 📥 Data Loading & Initial Inspection
- Loading the anonymized CSV dataset
- Viewing the first few rows, shape, and column types
- Checking for missing values and duplicates

### 2. 🔍 Exploratory Data Analysis (EDA)
- Distribution of the target variable (CKD vs non-CKD)
- Feature distributions across age groups and medical aid bands
- Correlation heatmaps
- Box plots and histograms for key blood markers

### 3. 🧹 Data Preprocessing
- Handling missing values (imputation strategies)
- Encoding categorical variables (e.g. age bands, medical aid tiers)
- Feature scaling / normalization
- Train-test split

### 4. ⚙️ Feature Engineering
- Selecting the most predictive features
- Creating derived features if applicable
- Dimensionality reduction (if used)

### 5. 🤖 Model Building
- Baseline model selection and rationale
- Models trained (e.g. Logistic Regression, Random Forest, XGBoost, etc.)
- Hyperparameter tuning
- Cross-validation

### 6. 📈 Model Evaluation
- Confusion Matrix
- Classification Report (Precision, Recall, F1-Score)
- ROC-AUC Curve
- Feature importance plot

### 7. 💾 Model Export *(if applicable)*
- Saving the best model using `joblib` or `pickle`
- Notes on how to load and run inference

### 8. 🧾 Conclusions & Recommendations
- Key findings from the model
- Clinical implications
- Limitations and next steps for research

---

## 🛠️ Tech Stack & Dependencies

| Tool | Purpose |
|---|---|
| Python 3.9+ | Core language |
| Pandas | Data manipulation |
| NumPy | Numerical operations |
| Matplotlib / Seaborn | Visualizations |
| Scikit-learn | ML models, preprocessing, evaluation |
| DecisionTree / RandomForest | Gradient boosting models |
| Joblib / Pickle | Model serialization |
| Jupyter Notebook | Development environment |

Install all dependencies via:

```bash
pip install -r requirements.txt
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/ckd-classification.git
cd ckd-classification
```

### 2. Set up a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Launch the notebook

```bash
jupyter notebook ckd_classification.ipynb
```

> If you don't have access to the dataset, you can still explore the notebook structure, visualizations, and model outputs already rendered in the cells.

---

## 🧠 Model Summary

| Model | Accuracy | F1-Score | AUC-ROC |
|---|---|---|---|
| Logistic Regression | — | — | — |
| KNNeighbour | — | — | — |
| Random Forest | — | — | — |
| GradientBoost | — | — | — |
| Best Model | **TBD** | **TBD** | **TBD** |
**To Be Determined**

> 📝 Fill in the above table with your actual results once evaluation is complete.

---

## 📉 Results & Evaluation

The best performing model achieved the following on the held-out test set:

- **Accuracy:** `100%`
- **Precision:** `100%`
- **Recall:** `100%`
- **F1-Score:** `100%`
- **AUC-ROC:** `1.00`

Key observations:
- The model performed particularly well in identifying CKD-positive cases with high recall, which is critical in a clinical screening context.
- Age group and specific blood markers (e.g. serum creatinine, eGFR) were among the top predictive features.
- Medical aid membership band showed a moderate correlation with CKD prevalence, likely reflecting access to care patterns.

---

## ⚖️ Ethical Considerations

This project was conducted with a strong commitment to responsible data use:

- ✅ All patient data was **fully anonymized** prior to being shared — no personally identifiable information (PII) was retained or used.
- ✅ The dataset was shared under a **research collaboration agreement** with a medical professional for academic purposes.
- ✅ No attempt was made to re-identify individuals from the dataset.
- ✅ The model is intended as a **research and screening aid**, not a replacement for clinical diagnosis.
- ✅ Results and findings are shared purely for academic and public health awareness purposes.

---

## 🙏 Acknowledgements

- The medical staff member at the Krugersdorp private hospital who facilitated access to the anonymized dataset and whose master's research inspired this project.
- The hospital administration for permitting responsible, anonymized data use for research.
- The open-source community for the tools and libraries that made this project possible.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE). The dataset itself is not covered under this license and may not be redistributed.

---

*Built with purpose — bridging Data Science and community healthcare in South Africa. 🇿🇦*
