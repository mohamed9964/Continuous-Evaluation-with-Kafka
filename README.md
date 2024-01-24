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

![F1-Scores for Random Forest Using Different Feature Selection Methods](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/F1-Scores_Random_Forest.png)
![F1-Scores for Logistic Regression Using Different Feature Selection Methods](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/F1-Scores_Logistic_Regression.png)
![Best Model F1-Score Comparison](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/Best_Model_F1-Score_Comparison.png)
![F1 Scores of Dynamic and Static Models Over Iterations](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/F1_Scores_Dynamic_Static_Over_Iterations.png)
![Model Performance Comparison on Different Datasets](https://github.com/mohamed9964/Continuous-Evaluation-with-Kafka/assets/53129060/Model_Performance_Comparison.png)
