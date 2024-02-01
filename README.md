# Breast-Cancer-Detection
# Project Title
A brief description of what your project does and the value it provides.

## Table of Contents
- [Dataset](#dataset)
- [Methodology](#methodology)
  - [Data Preprocessing](#data-preprocessing)
  - [Feature Selection](#feature-selection)
  - [Data Splitting](#data-splitting)
  - [Model Training](#model-training)
  - [Cross Validation](#cross-validation)
  - [Performance Evaluation](#performance-evaluation)
- [Results](#results)
  
## Dataset
The dataset used is the [Diagnostic Wisconsin Breast Cancer Dataset](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic), it contains 30 features holding information about geometry and texture of the cells, 

eg:
<ul>
  <li>Radius</li>
  <li>Perimeter</li>
  <li>Area</li>
  <li>Texture</li>
  <li>Smoothness</li>
  <li>Compactness</li>
  <li>Concavity</li>
  <li>Concave Points</li>
  <li>Symmetry</li>
  <li>Fractal Dimension</li>
</ul>

## Methodology

### Data Preprocessing
To clean the dataset, we must check for outliers, missing data and other data abnormalities, fortunately the only thing facing us here is outliers, to check for them used box plots for all of the features to see if there are outliers in the data, outliers were found in almots all the features, to solve this issue we can use min-max clipping, we calculated the min and max as `min = Q1 - 1.5(Q3 - q1)   max = min = Q3 + 1.5(Q3 - q1)`, then ran a loop on the dataset to replace the outliers with either the `min` or the `max` using those lines, where `x_clean` is the dataset without outliers
```
 #Remove outliers from the Dataframe
    X_clean[col].replace(list(X_clean[X_clean[col] > upper_bound][col]), upper_bound, inplace=True)
    X_clean[col].replace(list(X_clean[X_clean[col] < lower_bound][col]), lower_bound, inplace=True)
```
here are some screenshots of the box plots before and after the clipping:<br>
**Before clipping**:

![Screenshot from 2024-01-28 14-11-04](https://github.com/AbdullahAhmed30/Breast-Cancer-Detection/assets/101139791/7dfd439e-21e9-4f8a-b2d3-8e91698f89f8)
![Screenshot from 2024-01-28 14-11-49](https://github.com/AbdullahAhmed30/Breast-Cancer-Detection/assets/101139791/ecd2d712-f255-4886-975f-0df340ff0cf2)<br>
**After clipping**:

![Screenshot from 2024-01-28 14-12-14](https://github.com/AbdullahAhmed30/Breast-Cancer-Detection/assets/101139791/41a83307-da4c-4db0-9e02-2a5f863b9af6)
![Screenshot from 2024-01-28 14-12-31](https://github.com/AbdullahAhmed30/Breast-Cancer-Detection/assets/101139791/08b0e65a-ea92-40af-b0ff-cee7c98aa346)

The data was then normalized with a standard deviation of 1 and mean 0, to prevent data with larger values to skew the results in the expense of the features with the smaller values

### Feature Selection
In order to select the most significant features that will yeild the best perfomance, we calculated the spearman correlation coefficient between the features and the lables and removed any feature that yeilded a score below 0.5, then plotting the matrix gave the following 

![WhatsApp Image 2023-12-30 at 1 52 21 AM](https://github.com/AbdullahAhmed30/Breast-Cancer-Detection/assets/101139791/0f6e7dab-0bc0-44cc-8f42-0cdeba37a1ba)

### Data Splitting
The data was split with ratio of train to test 7:3, the same dataset was used before and split with ration 8:2 and we needed to experiment more, we used stratified random sampling to make sure the train data is represents the original dataset as much as possible

### Model Training
For each model (Random Forest, Logistic Regression, K-Nearest Neighbors, XGBoost, and SVM), explain why you chose it, how it works, and any specific parameters you tuned.

### Cross Validation
Explain why you used K-Fold cross-validation with k=5, how it helps in model validation, and what the results were.

### Performance Evaluation
Discuss how you calculated the confusion matrix and other metrics (accuracy, precision, F1 score, and recall). Explain what each metric indicates about your model's performance.

## Results
Discuss the results of your models, any insights you gained, and what these results mean.

## Contributing
Information about how other developers can contribute to your project.

## License
Information about the license.
