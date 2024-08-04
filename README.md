# Molecular Bioactivity Prediction

This project aims to analyze and predict molecular bioactivity using various machine learning techniques. The dataset used contains molecular data sourced from the ChEMBL database, with the primary objective of evaluating the druglikeness of compounds and predicting their bioactivity.

## Data Collection and Preparation

The dataset was sourced from the ChEMBL database and included columns such as `molecule_chembl_id`, `canonical_smiles`, `standard_value`, and `class`. The data was cleaned to remove any missing values and prepared for further analysis.

## Lipinski Descriptors Calculation

Christopher Lipinski's Rule of Five was applied to evaluate the druglikeness of compounds. According to this rule, a compound is likely to be druglike if it has:
- A molecular weight of less than 500 Dalton
- An octanol-water partition coefficient (LogP) of less than 5
- Fewer than 5 hydrogen bond donors
- Fewer than 10 hydrogen bond acceptors

These descriptors were calculated for each molecule in the dataset.

## Data Transformation and Visualization

The IC50 values in the `standard_value` column were converted to pIC50 values to ensure a more uniform distribution. This conversion involved:
- Converting IC50 values from nM to M
- Applying the negative logarithmic scale (-log10(IC50))
- Replacing the `standard_value` column with a new `pIC50` column

Visualizations were created to better understand the data, including class distribution, standard value distribution, pIC50 distribution, and SMILES length distribution.

## Model Building

PaDEL descriptors were calculated to create a matrix of molecular fingerprints, which served as the input feature set for model building. The dataset was split into training and test sets, and various regression models were trained to predict pIC50 values. The models included:
- `DecisionTreeRegressor`
- `ExtraTreesRegressor`
- `RandomForestRegressor`
- Several other models

## Model Evaluation

The models were evaluated based on their performance on both the training and test sets, with key performance metrics including R-squared and RMSE. The `RandomForestRegressor` and `ExtraTreesRegressor` models showed the best performance on the training set, while the `HistGradientBoostingRegressor` model demonstrated the best performance on the test set. The pIC50 values provided a more uniform distribution, aiding in more effective model training and evaluation.

## Repository Contents

The following documents are included in this repository:
1. **Data Collection**
2. **Exploratory Data Analysis (EDA)**
3. **Descriptive Calculator**
4. **Random Forest Model**
5. **Other Machine Learning Models**

These documents provide detailed insights and the codebase for the various steps of the project.
