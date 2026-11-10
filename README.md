# Richter's Predictor – Modeling Earthquake Damage

Predicts the ordinal `damage_grade` of 260,601 buildings hit by the 2015 Gorkha earthquake in Nepal, using building structure, location and ownership features.

| Grade | Meaning |
|---|---|
| 1 | Low damage |
| 2 | Medium damage |
| 3 | Near-complete destruction |

## What's in the notebook
- **Data analysis:** data quality checks, class imbalance (about 10% / 57% / 33%), implausible `age` values (up to 995), and damage by material and region
- **Modeling:** baseline, logistic regression, decision tree, random forest, XGBoost and LightGBM, then tuned LightGBM with and without class weighting
- **Suggestions to seismologists:** geography is the strongest predictor group (about 52% of total gain), followed by building material
- **Model comparison and challenges report**

## Results
Single stratified 80/20 split, 52,121 validation buildings.

| Model | Micro-F1 | Macro-F1 |
|---|---|---|
| LightGBM, tuned (255 leaves) | **0.750** | **0.701** |
| XGBoost | 0.744 | 0.690 |
| Random Forest | 0.726 | 0.655 |

Three-fold cross-validation of the best model gives 0.746 ± 0.002.

## Tech stack
Python, pandas, NumPy, scikit-learn, LightGBM, XGBoost, Matplotlib, Seaborn

## How to run
1. Clone the repo.
2. Install the libraries above.
3. Open `Earthquake_Damage_Prediction.ipynb` and run all cells. The data is already in `Data/`.

## Data
DrivenData, *Richter's Predictor: Modeling Earthquake Damage* (Nepal 2015 Gorkha earthquake survey data).
