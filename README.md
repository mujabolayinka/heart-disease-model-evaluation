# Beyond Accuracy: Evaluating Machine-Learning Models

## About the Project

This project compares two machine-learning classification models: Logistic Regression and Decision Tree. I used the UCI Heart Disease dataset to see how the models perform when evaluated using different metrics, rather than relying on accuracy alone.

I also looked at the prediction errors made by both models to understand where they made mistakes and how those mistakes differed.

## Dataset

The dataset was obtained from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/45/heart+disease).

This project uses the Cleveland subset of the dataset, which contains 303 records and 13 input features. The original target column (`num`) has values ranging from 0 to 4. For this project, I converted it into a binary target:

- **0:** No heart disease indicated in the dataset.
- **1:** Heart disease indicated in the dataset (original values 1–4).

## What I Did

The project followed these main steps:

1. Loaded and inspected the dataset.
2. Checked for missing values and examined the feature types.
3. Converted the original target into two classes.
4. Split the data into training and testing sets using an 80/20 split.
5. Filled missing values in `ca` and `thal` using the median and most frequent value, respectively, calculated from the training data.
6. Scaled the numerical features using StandardScaler.
7. Converted the categorical features into numerical form using OneHotEncoder.
8. Trained and evaluated Logistic Regression and Decision Tree classifiers.
9. Compared their results using different classification metrics and examined their prediction errors.

## Models and Evaluation

The two models were evaluated using the same test data.

The metrics used were:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

### Results

| Metric | Logistic Regression | Decision Tree |
|---|---:|---:|
| Accuracy | 86.89% | 75.41% |
| Precision | 81.25% | 68.57% |
| Recall | 92.86% | 85.71% |
| F1-score | 86.67% | 76.19% |

### Prediction Error Analysis

I also examined the incorrect predictions made by both models.

- Logistic Regression made 8 incorrect predictions.
- Decision Tree made 15 incorrect predictions.
- Both models made mistakes on 6 of the same records.
- Only Logistic Regression was wrong on 2 records.
- Only Decision Tree was wrong on 9 records.

This helped me compare not just the overall scores, but also the types of mistakes made by each model.

## Tools and Libraries

- Python
- Pandas
- Matplotlib
- Scikit-learn
- ucimlrepo
- Jupyter Notebook

## How to Run the Project

1. Download the repository as a ZIP file or clone it using Git.
2. Open the project folder.
3. Install the required packages:
   ```bash
   python -m pip install -r requirements.txt
   ```
4. Open `model_evaluation.ipynb` in Jupyter Notebook or VS Code.
5. Run the notebook cells from beginning to end.

An internet connection is needed to fetch the dataset from the UCI repository.

## Limitations

This project has some limitations:

- The dataset is relatively small, with only 303 records.
- The models were evaluated using one train-test split. Results may differ with another split.
- The original target values were grouped into two classes, so the distinctions between values 1 and 4 were not retained.
- No cross-validation or systematic hyperparameter tuning was performed.
- The dataset is historical, so the results may not represent other populations or present-day healthcare settings.
- This is an educational machine-learning project, not a clinically validated system. It should not be used to diagnose heart disease.

## Dataset Reference

Janosi, A., Steinbrunn, W., Pfisterer, M., & Detrano, R. (1989). *Heart Disease* [Dataset]. UCI Machine Learning Repository.

[https://doi.org/10.24432/C52P4X](https://doi.org/10.24432/C52P4X)

The dataset is available under the Creative Commons Attribution 4.0 International (CC BY 4.0) licence.
