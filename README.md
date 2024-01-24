# Continuous-Evaluation-with-Kafka

## Project Overview
This project demonstrates a continuous evaluation approach using Kafka to handle data in real-time, comparing the performance of static and dynamic machine learning models in the context of cybersecurity for predicting cyber-attacks.

### Part 1: Static Model
The static model utilizes the dataset `Static_dataset.csv` with 268,074 entries across 16 columns. It undergoes comprehensive data analysis, cleansing, feature engineering, and model training using Random Forest and Logistic Regression.

#### Data Analysis
- **Dataset Overview:** 268,074 entries, 16 columns.
- **Data Imbalance:** Balanced distribution of 'Target Attack' variable.

#### Statistical Analysis
1. **Correlation Matrix:** Heatmap revealing significant correlations.
2. **Distribution Analysis:** Histograms for numerical features.
3. **Outlier Detection:** Boxplots for outlier identification.
4. **Skewness Detection:** Calculated skewness for numerical features.

#### Data Cleansing and Feature Engineering
- Filled missing values, transformed timestamps, hashed and normalized categorical features.

#### Feature Selection
- Used Mutual Information, ANOVA F-test, and Chi-squared methods.

#### Model Training and Evaluation
- Trained Random Forest and Logistic Regression models.
- Best F1-Score: Random Forest with Chi-squared feature selection (0.86466).

#### Results Visualization
- ![F1-Scores for Random Forest](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/22eed8c7-59f9-490b-8857-9ec651922b70)
- ![F1-Scores for Logistic Regression](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/7d8d0226-26d8-4781-ab78-f375aba9b5f4)
- ![Best Model F1-Score Comparison](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/19d5dd4b-f08e-4664-b049-5a8a0b851eac)

### Part 2: Dynamic Model
The dynamic model processes data in windows of 1,000 records, continuously reevaluating and retraining when necessary.

#### Data Handling
- Processed data in windows of 1,000 records from Kafka stream.

#### Training Reevaluation Process
- Continuous reevaluation based on F1 score threshold (< 0.85).
- Retrained with historical and new data.

#### Model Evaluation
- Compared static and dynamic models using F1 score.

#### Results Visualization
- ![F1 Scores of Dynamic and Static Models Over Iterations](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/45974a37-e69e-4c27-864b-c242adf5d0c5)
- ![Model Performance Comparison on Different Datasets (Static Model vs. Dynamic Model)](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/4134ed3d-cd50-4de6-ae95-13010d9ff537)

### Advantages of the Dynamic Model
- Adaptability to new threats.
- Continuous learning from new and historical data.
- Balanced evaluation using F1 score.

### Limitations
- Significant computational resources for continuous retraining.
- Performance depends on the quality of input data.


### How to Use This Repository
- `dynamic_model.ipynb`: Notebook for the dynamic model implementation.
- `static_model.ipynb`: Notebook for the static model implementation.

## Conclusion
The project emphasizes the need for adaptive machine learning models in cybersecurity and the importance of selecting appropriate metrics for performance evaluation and resource management.

