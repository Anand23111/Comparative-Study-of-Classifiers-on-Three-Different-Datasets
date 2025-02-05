
# Comparative Study of Classifiers on Three Different Datasets

This repository presents a comparative study of four popular classification algorithms: Decision Tree, Random Forest, XGBoost, and AdaBoost. The study evaluates these classifiers on three distinct datasets:

1. **Medical Biopsy Dataset** - A binary classification task where the target variable indicates whether a patient is healthy or has cancer.
2. **Fetal Health Dataset** - A multi-class classification task where the target variable indicates the health status of a fetus.
3. **Banking Marketing Dataset** - A binary classification task to predict whether a customer subscribed to a term deposit.

The classifiers are evaluated using 5-fold cross-validation and the following metrics:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**
- **AUC-ROC** (Area Under the ROC Curve)

Additionally, **ROC curves** and **2D decision boundary visualizations** are plotted to help visualize model performance.

## Datasets

1. **Medical Biopsy Dataset**: This dataset is used for binary classification where the target variable (`Biopsy`) indicates whether a patient is Healthy or has Cancer.
2. **Fetal Health Dataset**: A multi-class classification dataset where the target variable (`fetal health`) takes values 1, 2, or 3.
3. **Banking Marketing Dataset**: A binary classification task where the target variable (`y`) indicates whether a customer subscribed to a term deposit (yes/no).

## Classifiers Used

### 1. **Decision Tree Classifier**
- Standard decision tree classifier to perform classification on all three datasets.
- 5-fold cross-validation is performed, and results are recorded for accuracy, precision, recall, F1 score, and AUC-ROC.

### 2. **Random Forest Classifier**
- Random Forest classifier with 100 trees is used for all datasets.
- Similar evaluation as Decision Tree, including plotting decision boundaries and ROC curves.

### 3. **XGBoost Classifier**
- XGBoost, an optimized gradient boosting algorithm, is used for classification.
- Same evaluation metrics and visualizations are generated.

### 4. **AdaBoost Classifier**
- AdaBoost, an ensemble method, is applied and evaluated using the same procedure.
  
## Data Preprocessing

For each dataset, the following preprocessing steps are performed:

1. **Loading and Concatenation**: If required, partial datasets are concatenated into a single DataFrame.
2. **Handling Missing Values**: Non-numeric values are replaced with NaN, and NaN values are imputed with the mean of respective columns.
3. **Feature Selection**: Two features are selected for 2D visualizations.
4. **Train-Test Split**: Data is split using 5-fold cross-validation, with 20% of data kept for test/ROC curve plotting.
5. **Cross-Validation**: StratifiedKFold with 5 splits to ensure class distribution is preserved.
6. **Metrics Calculation**: 
   - **Accuracy**
   - **Precision**
   - **Recall**
   - **F1 Score**
   - **AUC-ROC**

## Experiments and Results

The results for each classifier are summarized in the following table (values are illustrative and should be replaced with actual results from your code):

### Example Cross-Validation Results:

| Classifier        | Dataset     | Accuracy | Precision | Recall | F1    | AUC-ROC |
|-------------------|-------------|----------|-----------|--------|-------|---------|
| Decision Tree     | Dataset 1   | 0.90     | 0.88      | 0.92   | 0.90  | 0.93    |
| Decision Tree     | Dataset 2   | 0.91     | 0.90      | 0.89   | 0.89  | 0.90    |
| Decision Tree     | Dataset 3   | 0.88     | 0.85      | 0.84   | 0.84  | 0.89    |
| Random Forest     | Dataset 1   | 0.93     | 0.91      | 0.95   | 0.93  | 0.96    |
| Random Forest     | Dataset 2   | 0.94     | 0.93      | 0.92   | 0.92  | 0.95    |
| Random Forest     | Dataset 3   | 0.90     | 0.88      | 0.87   | 0.87  | 0.91    |
| XGBoost           | Dataset 1   | 0.94     | 0.93      | 0.96   | 0.94  | 0.96    |
| XGBoost           | Dataset 2   | 0.95     | 0.94      | 0.93   | 0.94  | 0.96    |
| XGBoost           | Dataset 3   | 0.91     | 0.89      | 0.89   | 0.89  | 0.92    |
| AdaBoost          | Dataset 1   | 0.91     | 0.89      | 0.92   | 0.90  | 0.94    |
| AdaBoost          | Dataset 2   | 0.93     | 0.92      | 0.90   | 0.91  | 0.94    |
| AdaBoost          | Dataset 3   | 0.89     | 0.86      | 0.84   | 0.85  | 0.90    |

## Illustrative Results

- ROC curves are plotted for each dataset and classifier combination.
- 2D decision boundaries are visualized by selecting two numeric features at a time.

## Conclusion

The study compares four classification algorithms—Decision Tree, Random Forest, XGBoost, and AdaBoost—across three datasets. Results suggest that ensemble methods like Random Forest, XGBoost, and AdaBoost generally perform better than a single Decision Tree. However, performance may vary based on data characteristics, class distribution, and hyperparameter tuning.

## How to Run

To run the experiments, clone this repository and follow these steps:

```bash
git clone https://github.com/yourusername/classifier-comparison.git
cd classifier-comparison
# Install required dependencies
pip install -r requirements.txt
# Run the analysis script
python run_classifiers.py
