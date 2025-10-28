# 🍽️ Obesity Risk Prediction

How likely are you to be overweight, normal-weight, or obese — based on your daily habits?  
This project explores that question using **machine learning and logistic regression** to classify individuals into obesity levels using lifestyle and anthropometric data.

---

## 📊 Overview

- **Goal:** Predict a person’s obesity level based on lifestyle and health factors  
- **Models Used:** Logistic Regression (One-vs-All and One-vs-One approaches)  
- **Tools:** Python, scikit-learn, pandas, seaborn, matplotlib  
- **Dataset:** UCI “Obesity Risk Prediction” dataset (2,111 samples, 17 features)

---

## 🧠 Workflow

1. **Data Loading & Cleaning**  
   - Used UCI dataset with no missing values  
   - Contained both numerical and categorical features (age, gender, diet, activity, etc.)

2. **Exploratory Data Analysis (EDA)**  
   - Explored relationships between physical parameters (height, weight, activity levels) and obesity categories  
   - Visualized obesity level distribution:

   ![Obesity Distribution](results/Distribution%20of%20Obesity%20Levels.png)

3. **Feature Engineering & Scaling**  
   - Standardized numerical columns using `StandardScaler`  
   - Applied one-hot encoding to categorical variables (e.g., gender, food habits, transport)

4. **Model Training & Evaluation**  
   - Used Logistic Regression for multi-class classification  
   - Compared **One-vs-All (OvA)** and **One-vs-One (OvO)** approaches  

   | Strategy | Accuracy |
   |-----------|-----------|
   | One-vs-All | 76.12% |
   | One-vs-One | 92.20% |

   The **One-vs-One** strategy significantly improved accuracy, showing that pairwise class boundaries capture nuanced patterns better in lifestyle data.

---

## 🔍 Feature Importance

### One-vs-All
![Feature Importance OvA](results/Feature%20Importance%20(One%20vs%20All).png)

### One-vs-One
![Feature Importance OvO](results/Feature%20Importance%20(One%20vs%20One).png)

> **Key Findings:**
> - **Transport & Lifestyle Habits:**  
>   Walking, using public transportation, and regular physical activity (FAF) are strong indicators of lower obesity risk.  
> - **Caloric Intake & Family History:**  
>   High-calorie intake (CALC, FAVC) and family history of overweight correlate strongly with obesity.  
> - **Water Intake (CH₂O)** and **Meal Frequency (NCP)** also show measurable impact.  

The results align well with real-world expectations — lifestyle, diet, and activity patterns collectively determine weight category.

---

## 🧩 Inference & Discussion

The **Obesity Risk Prediction model** demonstrates that even simple **logistic regression** can effectively model health-related behaviors if data is clean and representative.

- The **One-vs-One classifier** achieved **92.2% accuracy**, confirming strong predictive ability.  
- The model captures **behavioral, genetic, and physiological** contributors to obesity.
- It provides **transparent interpretability**, helping health researchers trace which habits contribute most to risk.

> **Interpretation:**  
> A sedentary person with frequent caloric intake and family obesity history is more likely to fall under *Obesity Type I–III*.  
> Meanwhile, high hydration, active lifestyle, and moderate eating habits correlate with *Normal Weight*.

---

## ⚙️ Potential Extensions

- Add **neural network** models (e.g., shallow MLPs) for non-linear feature interactions  
- Build a **web app** that inputs habits and predicts obesity risk level  
- Incorporate explainability tools like **SHAP** to interpret feature contributions

---

## 🧾 Files

| File | Description |
|------|-------------|
| `Obesity_Risk_Prediction.ipynb` | Complete notebook with data preparation, training, and analysis |
| `results/` | Visual outputs (distribution and feature importance plots) |
| `README.md` | This documentation file |

---

## 📘 Skills Highlighted

- Logistic Regression (One-vs-All & One-vs-One Classification)  
- Data Cleaning and Feature Encoding  
- Health & Lifestyle Data Interpretation  
- Model Evaluation and Explainability  

---

📍 *A data-driven exploration of how daily habits and environment shape health outcomes.*  
✍️ *Written by Rohith Roshan — with AI assistance.*
