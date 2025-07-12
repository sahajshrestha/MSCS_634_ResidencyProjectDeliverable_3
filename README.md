# MSCS 634 - Project Deliverable 3: Classification, Clustering, and Pattern Mining

## 📁 Dataset Summary
We used a modified heart disease dataset with 500+ records and ~13+ original attributes. Categorical features were one-hot encoded to support machine learning algorithms. The target variable `target` indicates presence (1) or absence (0) of heart disease.

---

## 1️⃣ Classification Models

### Models Used:
- Decision Tree Classifier
- K-Nearest Neighbors (KNN)

### Results:
| Model           | Accuracy | Notes |
|----------------|----------|-------|
| Decision Tree  | ~83%     | Good baseline, interpretable |
| KNN (k=5)       | ~86%     | Slightly better, but sensitive to feature scaling |

### 🔍 Insight:
Both models showed promising accuracy, with KNN performing slightly better after standardization. Confusion matrices and F1-scores helped identify model effectiveness on true positives.

---

## 2️⃣ Hyperparameter Tuning

- Decision Tree: Best `max_depth = 4` gave optimal generalization.
- KNN: Best `k = 5` balanced bias and variance.
  
### 🔍 Insight:
Tuning improved model performance. Visualization of accuracy vs. depth/`k` confirmed sweet spots before overfitting began.

---

## 3️⃣ Clustering (KMeans)

### Process:
- Used `KMeans` with 2 clusters (since target has 2 classes).
- Reduced dimensions using PCA for 2D plotting.

### 🔍 Insight:
Clusters roughly aligned with actual disease status. Though not perfect, unsupervised learning showed the natural separability of the dataset even without labels.

---

## 4️⃣ Association Rule Mining (Apriori)

### Process:
- Applied Apriori on binary-encoded features like chest pain (`cp`), fasting blood sugar, etc.
- Discovered strong rules with high confidence and lift.

### Example Rule Found:
- **If cp_2 is present → target = 1**
  - Confidence: 78.5%
  - Lift: 1.53

### 🔍 Insight:
Strong patterns were uncovered showing symptom combinations linked to heart disease. Useful for rule-based health monitoring.

---

## 💡 Challenges
- Feature encoding required careful handling to preserve label integrity.
- KNN needed standardized features to perform well.
- Choosing min support/confidence thresholds in Apriori required trial-and-error.

---

## ✅ Tools & Libraries
- Python (Pandas, Scikit-learn, Seaborn, Matplotlib)
- mlxtend (Apriori)
- Jupyter Notebook

---

## 🧠 Conclusion
This deliverable explored classification, clustering, and pattern mining on a healthcare dataset. Each model provided different perspectives on the data and deepened our understanding of feature relationships, which can be applied in real-world diagnosis or patient segmentation.

