# 🌾 Agricultural Land Classification — CNN vs CNN–Transformer Hybrid

Can a simple convolutional network accurately classify agricultural land from low-resolution satellite images?  
And does adding Transformer-based attention meaningfully improve performance?

This project explores that question by comparing a **baseline CNN** with a **hybrid CNN–Transformer architecture**.

---

## 📊 Overview

- **Goal:** Classify satellite images into `agri` and `non_agri`
- **Techniques:** Convolutional Neural Networks, Transformer Encoder (ViT-style attention)
- **Tools:** Python, PyTorch, torchvision, scikit-learn, matplotlib
- **Dataset:** Low-resolution satellite imagery (64×64), balanced binary classes

---

## 🧠 Workflow

1. **Data Acquisition & Preparation**  
   - Downloaded and extracted `.tar` dataset  
   - Organized class folders  
   - Applied resizing and data augmentation  
   - Split into training and validation sets  

2. **Baseline CNN Model**  
   - Built a 3-layer convolutional network  
   - Used Batch Normalization and ReLU activations  
   - Applied Adaptive Average Pooling for classification  
   - Trained using CrossEntropyLoss and Adam optimizer  

3. **Hybrid CNN–Transformer Model**  
   - Reused trained CNN backbone as feature extractor  
   - Converted feature maps into tokens  
   - Applied multi-head self-attention using Transformer Encoder  
   - Used CLS token for final classification  

4. **Model Evaluation**  
   - Compared confusion matrices  
   - Evaluated precision, recall, F1-score  
   - Analyzed error patterns between models  

---

## 📈 Results

| Model | Validation Accuracy | Misclassifications | Key Insight |
|--------|---------------------|-------------------|--------------|
| **CNN** | ~99.7% | 4 / 1200 | Local convolutional features are sufficient |
| **Hybrid CNN–Transformer** | ~99.75% | 3 / 1200 | Attention adds negligible improvement |

---

### 🔹 CNN Confusion Matrix
```
[[609   4]
 [  0 587]]
```

### 🔹 Hybrid CNN–Transformer Confusion Matrix
```
[[613   0]
 [  3 584]]
```

---

## 🔍 Key Insights

- Both models achieved near-perfect classification performance.
- The performance difference is statistically insignificant (1 sample).
- The dataset is low complexity and easily separable.
- CNN alone extracts sufficient spatial features.
- Transformer-based global attention does not provide meaningful gains in this setting.
- Increased model complexity does not guarantee better performance.

---

## 🧩 Technical Takeaway

For low-resolution and low-complexity satellite imagery:

- A well-designed CNN is efficient and sufficient.
- Hybrid architectures should be justified by dataset complexity.
- Model capacity must match data difficulty.

This project builds architectural intuition on when attention mechanisms are necessary — and when they are not.
