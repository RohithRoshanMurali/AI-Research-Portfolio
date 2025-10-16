# 🌧️ Rainfall Prediction Classifier

Can we predict if it’s going to rain tomorrow?  
That’s exactly what this project tries to do using **machine learning** and real meteorological data.  
By bringing together features like **temperature, humidity, pressure, and sunshine hours**,  
the model learns how different conditions interact to cause rainfall in a specific region.

---

## 📊 Overview

- **Goal:** Predict rainfall for the next day (Yes / No – binary classification)  
- **Models Used:** Random Forest, Decision Tree, Logistic Regression  
- **Tools:** Python, scikit-learn, pandas, matplotlib, seaborn  
- **Output:** “Rain Tomorrow” → Yes / No  

The dataset includes daily weather details — from morning humidity to evening sunshine —  
all of which influence the final prediction.

---

## 🧠 Workflow

1. **Data Loading & Cleaning:**  
   Filled missing values, encoded categorical features, and scaled numeric ones.  

2. **EDA (Exploratory Data Analysis):**  
   Checked how factors like humidity, temperature, and pressure correlate with rainfall.  

3. **Feature Selection:**  
   Identified the top meteorological factors influencing rainfall using feature importance scores.  

4. **Model Training:**  
   Trained and compared Random Forest, Decision Tree, and Logistic Regression models to find the best performer.  

5. **Model Evaluation:**  
   Evaluated results using accuracy, F1-score, and a confusion matrix for balance and reliability.  

---

## 📈 Results

| Metric | Value |
|--------|--------|
| **Accuracy** | 0.85 |
| **F1-Score** | 0.83 |
| **Best Model** | Random Forest Classifier |

### 🔹 Confusion Matrix

The Random Forest model predicted most of the non-rainy days correctly and handled a good share of rainy ones too.

![Confusion Matrix](results/Confusion%20Matrix.png)

> **Interpretation:**  
> Out of 1,512 test samples, **1,273 were classified correctly**.  
> It slightly underpredicts rainfall (a few false negatives) but performs well overall —  
> a common pattern when working with imbalanced weather datasets.

---

## 🌤️ Feature Importance

So what really drives rainfall? Here’s what the model figured out:

![Feature Importance](results/Important%20Features.png)

### 🔹 Top Takeaways
- Afternoon **Humidity (3pm)** and **Pressure (3pm)** are the most dominant predictors.  
- **Sunshine hours** and **Wind gust speed** also play a notable role.  
- **Temperature** matters, but not as much — showing that moisture and pressure dominate the prediction.

> **Interpretation:**  
> It makes sense meteorologically —  
> higher humidity and lower pressure increase rainfall chances,  
> while longer sunshine hours usually mean clearer skies.

---

## 🔍 Inference

The model captures the core physics of weather quite well:  
**High humidity + low pressure = high chance of rain.**

Though it’s not a complete forecasting system, it proves how ML models  
can complement traditional meteorology — fast, explainable, and accurate enough for insights.

### ⚙️ Potential Improvements
- Handle class imbalance with **SMOTE** or weighted models  
- Fine-tune hyperparameters to improve recall on rainy days  
- Deploy it as a small web app for **real-time rainfall prediction**

---

## 🧩 Files

| File | Description |
|------|-------------|
| `Rainfall_Prediction_Classifier.ipynb` | Full notebook with all steps — from cleaning to modeling |
| `data/` | Cleaned dataset used for training |
| `results/` | Visual outputs and performance plots |
| `README.md` | This documentation file |

---

## 📘 Skills Highlighted

- Machine Learning (Classification & Model Evaluation)  
- Data Cleaning and Feature Engineering  
- Environmental and Meteorological Data Analysis  
- Model Interpretability and Visualization  

---

📍 *Another step forward in using AI for smarter environmental insights.*  
✍️ *Written by Rohith Roshan — with AI assistance.*
