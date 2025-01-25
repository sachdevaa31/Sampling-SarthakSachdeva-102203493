# Sampling Assignment - Model Performance Evaluation

## Problem Statement
The objective of this assignment was to evaluate the impact of different sampling techniques and machine learning models on a given imbalanced dataset. The goals included:

- Balancing the dataset.
- Creating samples using various sampling techniques.
- Training and evaluating different machine learning models.
- Comparing performance to identify the best sampling technique and model combination.

---

## Methodology

### 1. Dataset Preparation and Balancing
- The dataset was loaded, and the target variable's class distribution was checked.
- The dataset was imbalanced, so it was balanced using **SMOTE** (Synthetic Minority Oversampling Technique) to ensure an equal number of samples for each class.

### 2. Sampling Techniques
Five different sampling techniques were applied to generate subsets of the balanced dataset:
- **Simple Random Sampling**
- **Stratified Sampling**
- **Cluster Sampling**
- **Systematic Sampling**
- **Convenience Sampling**

### 3. Model Training and Evaluation
Five machine learning models were trained on the sampled datasets:
- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier
- Support Vector Classifier (SVC)
- K-Nearest Neighbours (KNN)

### 4. Hyperparameter Tuning
- Hyperparameter optimization was performed on **Random Forest** using **GridSearchCV** to improve its performance further.

### 5. Evaluation Metrics
The models were evaluated using:
- **Test Accuracy**: Performance on a test set.
- **Cross-Validation Accuracy**: Consistency across folds during cross-validation.

---

## Results Summary

### Test Accuracy (Train-Test Split)

| Model                 | Test Accuracy (%) |
|-----------------------|-------------------|
| Logistic Regression   | 93.55            |
| Decision Tree         | 95.16            |
| Random Forest         | 98.39            |
| SVC                   | 98.39            |
| K-Nearest Neighbours   | 93.55            |

### Cross-Validation Accuracy

| Model                 | CV Accuracy (%)  |
|-----------------------|------------------|
| Logistic Regression   | 92.21           |
| Decision Tree         | 95.76           |
| Random Forest         | 99.67           |
| SVC                   | 96.75           |
| K-Nearest Neighbours   | 86.70           |

---

## Best Hyperparameters for Random Forest
- **max_depth**: None (no limit on tree depth)  
- **min_samples_split**: 2  
- **n_estimators**: 50  
- **Accuracy**: 99.67% (Cross-Validation)

---

## Analysis

### 1. Random Forest
- The best-performing model with an impressive **98.39% Test Accuracy** and **99.67% Cross-Validation Accuracy**.
- Hyperparameter tuning via GridSearchCV further optimized its performance.

### 2. SVM
- Performs equally well as Random Forest on the test set (**98.39% Test Accuracy**).
- Slightly lower cross-validation accuracy (**96.75%**), but still highly robust.

### 3. Decision Tree
- Very good performance (**95.16% Test Accuracy**), but slightly lower than Random Forest due to its tendency to overfit.

### 4. Logistic Regression
- Good results (**93.55% Test Accuracy** and **92.21% CV Accuracy**) but less effective than non-linear models for this dataset.

### 5. K-Nearest Neighbours (KNN)
- The weakest performer among the models (**93.55% Test Accuracy** and **86.70% CV Accuracy**).
- Performance might improve by tuning the value of \( k \) and weighting the neighbours.

---

## Recommendations

### 1. Random Forest and SVM
- These are the top-performing models and should be prioritized for practical deployment.
- Random Forest provides slightly more consistent performance.

### 2. Decision Tree
- It’s simpler and faster than Random Forest but less robust. Consider it when interpretability or speed is a priority.

### 3. Logistic Regression
- Works well for simpler, linearly separable datasets but falls short compared to non-linear models here.

### 4. K-Nearest Neighbours
- Consider fine-tuning the hyperparameters (e.g., \( k \), weights, and distance metrics) if you wish to explore improvements.

---

## Conclusion

- **Random Forest** and **SVM** are the best models for this dataset, with **Random Forest** being slightly more consistent.
- Sampling techniques significantly impact model performance; further exploration may refine results.
- This analysis demonstrates the importance of **balancing data** and **tuning hyperparameters** for machine learning success.

