# Mushroom Classification using Machine Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML-orange?logo=scikit-learn)
![Best Model](https://img.shields.io/badge/Best%20Model-Random%20Forest-brightgreen)
![Status](https://img.shields.io/badge/Status-Completed-green)

## Project Overview

This project classifies mushrooms as **poisonous** or **edible** based on their physical characteristics. Four classification algorithms were built and compared: **KNN, Decision Tree, Random Forest, and Logistic Regression**.

---

## Dataset

- **Source:** [Mushroom Dataset — Kaggle (UCI)](https://www.kaggle.com/datasets/uciml/mushroom-classification/data)
- **Samples:** 8,124 mushrooms × 23 columns (after cleaning: 5,644)
- **Target:** `class` → `e` = edible (0), `p` = poisonous (1)
- **All features are categorical** (encoded with LabelEncoder)

| Feature | Description |
|---------|-------------|
| `cap-shape` | Shape of mushroom cap |
| `cap-color` | Color of mushroom cap |
| `odor` | Smell of the mushroom |
| `gill-color` | Color of gills |
| `stalk-root` | Root type of stalk |
| `spore-print-color` | Color of spore print |
| `habitat` | Where mushroom grows |
| `...` | 23 features total |

---

## Data Preprocessing

- Replaced `?` values in `stalk-root` with `None` → dropped rows with missing values
- Applied **LabelEncoder** to all 23 categorical columns
- Train/Test split: **80% / 20%** (`random_state=42`)
- Final dataset after cleaning: **5,644 samples**

---

## Models & Results

| Model | Precision | Recall | F1-Score | Accuracy |
|-------|-----------|--------|----------|----------|
| KNN (k=1) | 0.993 | 0.991 | 0.992 | ~99% |
| **Decision Tree** | **1.000** | **1.000** | **1.000** | **100%** |
| **Random Forest** | **1.000** | **1.000** | **1.000** | **100%** |
| Logistic Regression | 0.961 | 0.927 | 0.944 | 96% |

### Best Models: Decision Tree & Random Forest

Both achieved **100% accuracy** — this is expected for the Mushroom dataset as it has very strong categorical separators (especially `odor` and `spore-print-color`).

**Random Forest** selected as the final best model due to better generalization ability compared to a single Decision Tree.

---

## Key Findings

- **KNN:** Best k = 1 — dataset has very tight, well-separated clusters
- **Decision Tree & Random Forest:** Perfect classification — categorical features like `odor` are extremely predictive
- **Logistic Regression:** 96% accuracy — struggles with non-linear categorical boundaries

---

## Visualizations

- **KNN Tuning Plot** — Train vs Test accuracy across k = 1–30
- **Confusion Matrices** — for all 4 models
- **Metrics Comparison Table** — Precision, Recall, F1 side-by-side

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| `Python` | Core language |
| `Pandas / NumPy` | Data manipulation |
| `Matplotlib / Seaborn` | Visualization |
| `Scikit-learn` | All ML models & evaluation |

---

## How to Run

```bash
# Clone the repository
git clone https://github.com/husan-ai/mushroom-classification.git
cd mushroom-classification

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook Qo_ziqorinlar_bo_yicha_ML_All_type_.ipynb
```

---

## Requirements

```
numpy
pandas
matplotlib
seaborn
scikit-learn
jupyter
```

---

## Future Improvements

- [ ] Use **cross-validation** instead of single train/test split
- [ ] Try **feature importance** analysis to find the most predictive features
- [ ] Handle `stalk-root` missing values with imputation instead of dropping
- [ ] Add **ROC Curve** comparison for all models
- [ ] Deploy as a mushroom safety checker web app with **Streamlit**

---

## Author

**Husan**  
ML | DL | NLP  
GitHub: [@husan-ai](https://github.com/husan-ai)
