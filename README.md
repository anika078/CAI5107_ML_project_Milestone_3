# Hybrid SMOTE-Tomek and Ensemble Learning for Parkinson's Disease Staging Classification

## Author
**Name:** Anika Anjum  
**UID:** U74386931  
**Email:** anikaanjum@usf.edu  
**Course:** CAI5107 - Machine Learning

---

## Project Overview
This project implements a hybrid approach combining SMOTE-Tomek data balancing with ensemble learning methods for binary classification of Parkinson's Disease staging (Early Stage 1 vs Advanced Stage 4) using tablet-based digital biomarkers.

---

## Novel Contributions
1. **Hybrid SMOTE-Tomek Sampling:** Addresses 2.89:1 class imbalance through synthetic oversampling and noise removal
2. **Systematic Model Architecture Comparison:** Evaluates 12 models across 4 architecture types (Baseline, Ensemble, Single Classifier, Voting)
3. **Feature Importance Analysis:** Identifies discriminative biomarkers across Motor, Speech, Memory, and Executive Function categories

---

## Dataset
- **Total Patients:** 74 (55 Early Stage, 19 Advanced Stage)
- **Features:** 57 tablet-based digital biomarkers
- **Categories:** Motor (39), Speech (11), Executive Function (4), Memory (3)
- **Train/Test Split:** 70/30 stratified split

---

## Methods
| Model Type | Models |
|------------|--------|
| Baseline | CART (Decision Tree) |
| Ensemble | Random Forest, XGBoost, AdaBoost |
| Single Classifier | Logistic Regression, SVM, KNN, LDA |
| Voting Ensemble | 4 combinations (LR+RF+XGB, SVM+LR+XGB, RF+SVM+LR, XGB+SVM+LR+RF) |

---

## Key Results

### Best Model Performance
| Model | Data | F1 | Accuracy | Recall | Precision |
|-------|------|-----|----------|--------|-----------|
| Random Forest | SMOTE-Tomek | **0.923** | 0.957 | 1.000 | 0.857 |
| Voting Ensembles (4) | Original | 0.909 | 0.957 | 0.833 | 1.000 |
| KNN | Original | 0.909 | 0.957 | 0.833 | 1.000 |
| CART (Baseline) | Original | 0.769 | 0.870 | 0.833 | 0.714 |

### Improvement Over Baseline
- **+20% F1-Score** improvement (0.769 → 0.923)
- **Perfect Recall (1.000)** achieved—no advanced-stage patients missed

---

## Repository Structure
```
├── Data/
│   ├── Parkinsons_vs_Control_Dataset.csv
│   └── feature_description_modified.csv
├── Code/
│   ├── Milestone_III_ML_Project.ipynb
├── README.md

```

---

## How to Run

###  Google Colab 
1. Open the notebook in Google Colab
2. Upload the dataset files to `/content/`
3. Run all cells sequentially

---

## Key Findings
- SMOTE-Tomek only benefits bagging-based ensembles (Random Forest: +15.4%)
- Voting ensembles dominate on original data (F1=0.909)
- Motor features alone match all-feature performance (F1=0.923)
- Non-motor features show clinical relevance in feature importance despite limited category-level performance

---

## References
- Original Paper: "Classification of Parkinson's Disease and its Stages using Machine Learning"
- Dataset: Tablet-Based Assessment component from Parkinson's Disease digital biomarker collection

---

## License
This project is for academic purposes as part of CAI5107 coursework at University of South Florida.
