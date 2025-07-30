
# ❤️ Heart Disease Clinical Dashboard

A Power BI dashboard to analyze heart disease trends using clinical data.

![Heart Disease Dashboard](Images/heart_dashboard.png)

---

## 📊 Key Insights

- **Total Patients:** 1,025
- **Heart Disease Cases:** 526
- **Heart Disease Prevalence:** 51.3%
- **Average Age:** 54
- **Average Cholesterol:** 246
- **Average Resting BP:** 131.61

---

## 📌 Visualizations & Highlights

### 🧬 Demographics

* **Gender Distribution**:

  * **69.56% Male**, **30.44% Female**
  * Heart disease is more prevalent among male patients in the dataset.

* **Age Distribution**:

  * The **majority of patients** fall within the **50–59 years** age range, indicating middle-aged individuals are more represented.

* **Thalassemia Status**:

  * The most common type is **Reversible Defect (53.07%)**.
  * Other types include **Fixed Defect**, **Normal**, and **Unknown (6.24%)**.
  * *Note: Patients with "Unknown" thalassemia status are excluded from analysis for data consistency.*

---

### 🩺 Clinical Indicators

* **High Cholesterol Patients**:

  * **503 patients** have cholesterol levels **greater than 240 mg/dl**, considered high risk.

* **High-Risk Patients**:

  * Patients with **both high cholesterol and high ST depression (`oldpeak > 2`)** are considered **clinically high risk** for heart disease.

* **Exercise-Induced Angina (Exang)**:

  * A majority of **heart disease cases** are found among patients who **do not report angina during exercise**, which may seem counterintuitive but could be influenced by exercise avoidance or underlying conditions.

---

### ⚠️ Risk Group Analysis

* **Heart Disease by Age Group**:

  * The **prevalence of heart disease increases with age**, especially in patients above 50 years.

* **Chest Pain Type Correlation**:

  * **Typical Angina** and **Asymptomatic chest pain** types show a **strong correlation with heart disease**.

* **ST Depression (Oldpeak) Distribution**:

  * Patients with **lower ST depression** values (closer to 0) tend to have **higher heart disease prevalence**, suggesting that ST depression alone may not be a strong predictor in isolation but should be combined with other factors.

---

## ⚙️ Tools Used

- **Power BI**: Data modeling, measures (DAX), and dashboarding
- **DAX**: Custom measures such as:
  ```dax
  Total Patients = COUNTROWS('heart')
  Heart Disease Cases = CALCULATE(COUNTROWS('heart'), 'heart'[target] = 1)
  High_Cholesterol_Patients = CALCULATE(COUNTROWS('heart'), 'heart'[chol] > 240)
  ```

---

## 📁 Dataset

* **Age**: Patient age in years

* **Sex**: 1 = Male, 0 = Female

* **Chest Pain Type** (4 values):

  * 0 = Typical Angina
  * 1 = Atypical Angina
  * 2 = Non-anginal Pain
  * 3 = Asymptomatic

* **Resting Blood Pressure** (in mm Hg)

* **Serum Cholesterol** (in mg/dl)

* **Fasting Blood Sugar**: >120 mg/dl (1 = True, 0 = False)

* **Resting Electrocardiographic Results**:

  * 0 = Normal
  * 1 = ST-T Wave Abnormality
  * 2 = Probable or Definite Left Ventricular Hypertrophy

* **Maximum Heart Rate Achieved**

* **Exercise-Induced Angina**: 1 = Yes, 0 = No

* **Oldpeak**: ST depression induced by exercise relative to rest

* **Slope of the Peak Exercise ST Segment**:

  * 0 = Upsloping
  * 1 = Flat
  * 2 = Downsloping

* **Number of Major Vessels Colored by Fluoroscopy**: 0–3

* **Thalassemia** (`thal`):

  * 0 = Normal
  * 1 = Fixed Defect
  * 2 = Reversible Defect

* **Target**: 1 = Presence of heart disease, 0 = No heart disease

---

## 🧠 Purpose

To help clinicians and health analysts:
- Identify high-risk heart disease profiles
- Visualize key patterns in cardiac health data
- Make informed decisions using data-driven insights
