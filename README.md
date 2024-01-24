# Continuous-Evaluation-with-Kafka

## Project Overview
This project demonstrates a continuous evaluation approach using Kafka to handle data in real-time. It compares the performance of static and dynamic machine learning models in the context of cybersecurity, specifically for the task of predicting cyber-attacks.

### Part 1: Static Model
The static model utilizes a dataset (`Static_dataset.csv`) of 268,074 entries across 16 columns. The dataset features a balanced distribution of the target variable (attack/no attack). A comprehensive data analysis includes correlation matrices, distribution analysis, outlier detection, and skewness detection. After data cleansing and feature engineering, the model was trained using feature selection methods such as Mutual Information, ANOVA F-test, and Chi-squared.

#### Model Training and Evaluation
Two models were trained: Random Forest and Logistic Regression. The Random Forest model, with Chi-squared feature selection, achieved the best F1-Score of 0.86466, outperforming Logistic Regression.

### Part 2: Dynamic Model
The dynamic model processes data in windows of 1,000 records and reevaluates its performance continuously, triggering retraining whenever necessary. It proves to be adaptive and often outperforms the static model after retraining sessions.

#### Advantages of the Dynamic Model
- Adaptability to new threats
- Continuous learning from new and historical data
- Balanced evaluation using the F1 score

#### Limitations
- Significant computational resources for continuous retraining
- Performance depends on the quality of input data

## Results
The results are visualized in the attached images, reflecting the F1-Scores and accuracies of the models using different feature selection methods and over iterations.

### How to Use This Repository
- `dynamic_model.ipynb`: Notebook for the dynamic model implementation.
- `static_model.ipynb`: Notebook for the static model implementation.
- Results Images: Visual representations of the model's performance.

## Conclusion
This project underscores the necessity for machine learning models in cybersecurity to adapt to changing threat patterns and the importance of selecting appropriate performance metrics and managing resources efficiently.

![F1-Scores for Random Forest Using Different Feature Selection Methods](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/22eed8c7-59f9-490b-8857-9ec651922b70)
![F1-Scores for Logistic Regression Using Different Feature Selection Methods](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/7d8d0226-26d8-4781-ab78-f375aba9b5f4)
![Best Model F1-Score Comparison](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/19d5dd4b-f08e-4664-b049-5a8a0b851eac)
![F1 Scores of Dynamic and Static Models Over Iterations](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/45974a37-e69e-4c27-864b-c242adf5d0c5)
![Model Performance Comparison on Different Datasets](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/4134ed3d-cd50-4de6-ae95-13010d9ff537)
