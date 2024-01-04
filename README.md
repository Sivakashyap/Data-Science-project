-------------------------------------------Admission Predictor-------------------------------------------

This repository contains a Python script for predicting the admission status of a candidate based on certain input features. The script uses a Random Forest Classifier for prediction and performs data preprocessing steps, including data cleaning, transformation, dimensionality reduction using PCA, and manual feature scaling.

This code is a data preprocessing and machine learning pipeline for a college admission prediction task.

Importing Libraries:
   - `pandas`, `numpy`: For handling data and numerical operations.
   - `RandomForestClassifier` from `sklearn.ensemble`: For implementing a random forest classifier.
   - `LabelEncoder` from `sklearn.preprocessing`: For encoding categorical variables.
   - `seaborn` and `matplotlib.pyplot`: For data visualization.

Loading and Cleaning Data:
   - The code starts by loading a dataset from a CSV file (`DS project2.csv`) using Pandas.
   - Columns are renamed for better readability.
   - Missing values in the 'Rank' column are filled based on the median of subgroups defined by 'Branch', 'Gender', and 'Category'.
   - Duplicate rows based on 'Name' and 'Rank' are removed.
   - The 'Timestamp' column is dropped.
   - The shape of the DataFrame is printed before and after cleaning.

Data Transformation:
   - Categorical attributes ('Category', 'Gender', 'Branch', 'State', 'Output') are encoded using LabelEncoder.
   - Outliers in the 'Rank' column are removed based on the interquartile range (IQR) method.

PCA (Principal Component Analysis):
   - PCA is manually performed for dimensionality reduction.
   - The covariance matrix is calculated, and eigenvalues and eigenvectors are obtained.
   - Top principal components are chosen, and data is projected onto these components.
   - Feature scaling (Min-Max scaling) is performed manually.

Random Forest Classifier
   - A RandomForestClassifier is trained on the preprocessed data.

Data Visualization
   - A heatmap of the correlation matrix for multiple variables is plotted using seaborn and matplotlib.

User Input and Prediction
   - The user is prompted to input data for prediction (Name, Preferred Branch, Category Rank, Gender, State, and Category).
   - The user input is prepared as a DataFrame and projected onto the top principal components.
   - Feature scaling is applied to the user data.
   - The trained RandomForestClassifier is used to predict whether the user can join the college or not based on the admission criteria.

Output
   - The code outputs whether the user is eligible to join the college or not based on the model prediction.
