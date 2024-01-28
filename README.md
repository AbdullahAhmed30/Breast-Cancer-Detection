# Breast-Cancer-Detection
# Project Title
A brief description of what your project does and the value it provides.

## Table of Contents
- Usage
- Dataset
- Methodology
  - [Data Preprocessing](#data-preprocessing)
  - Feature Selection
  - Data Splitting
  - Model Training
  - Cross-Validation
  - Performance Evaluation
- Results
- Contributing
- License

## Installation
Detailed instructions on how to install, set up, and get the project running.

## Usage
Instructions to use your project, examples, screenshots, and tips.

## Dataset
Information about the dataset you used, how to download it, and how it's structured.

## Methodology

### Data Preprocessing
First, to know if there are any outliers, a box plot was plotted for all of the features, almost all of them had outliers, so we used min_max clipping, we calculated the min as `min = Q1 - 1.5(Q3 - Q1)` and the max as `max = Q3 + 1.5(Q3 - Q1)`, then

### Feature Selection
Describe why you chose the Spearman correlation coefficient for feature selection, how it works, and how you determined the threshold for low correlation.

### Data Splitting
Discuss why you split your data into a 7:3 train-test ratio. Explain if you used any specific strategies like stratified splitting.

### Model Training
For each model (Random Forest, Logistic Regression, K-Nearest Neighbors, XGBoost, and SVM), explain why you chose it, how it works, and any specific parameters you tuned.

### Cross-Validation
Explain why you used K-Fold cross-validation with k=5, how it helps in model validation, and what the results were.

### Performance Evaluation
Discuss how you calculated the confusion matrix and other metrics (accuracy, precision, F1 score, and recall). Explain what each metric indicates about your model's performance.

## Results
Discuss the results of your models, any insights you gained, and what these results mean.

## Contributing
Information about how other developers can contribute to your project.

## License
Information about the license.
