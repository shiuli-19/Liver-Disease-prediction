# Predicting Liver Disease Using Machine Learning

This notebook uses popular Python libraries to build and test a machine learning model that predicts whether a patient has liver disease based on their medical data. It’s all about finding the best approach to spot liver issues early.

Here’s the plan:  
- Problem Definition  
- Data  
- Evaluation  
- Features  
- Modeling  
- Experimentation & Results  

## 1. Problem Definition  
Given a set of clinical parameters of patients, can a machine learning model accurately predict whether a patient has liver disease or not? The goal is to build an optimized model that maximizes predictive performance.

## 2. Data  
The dataset used for this analysis is the Liver Patient Dataset (LPD), which contains medical records of patients.The data was sourced from Kaggle and consists of two files:
- **Train Dataset**: 30,691 records, 11 features
- **Test Dataset**: 2,109 records, 10 features
This dataset provides clinical attributes that help in predicting liver disease using various machine learning models.

## 3. Evaluation

To determine the most effective machine learning model for liver disease prediction, various evaluation metrics are considered:

- **Accuracy**: Measures the overall correctness of the model’s predictions across both diseased and non-diseased cases.
- **Recall**: Specifically assesses the model’s ability to correctly identify liver disease cases. This metric is **crucial** in medical applications where false negatives—missed diagnoses—can have serious consequences.

Since **early detection of liver disease** is vital for timely medical intervention, the focus is on selecting a model with **high recall**, ensuring that as many actual cases as possible are correctly identified. This approach helps minimize the risk of undiagnosed conditions, leading to better patient outcomes.


## Liver Disease Dataset Features (Updated with Ranges)

1. **Age**  
   - Age of the patient in years.

2. **Gender**  
   - Male (1) or Female (0).

3. **Total_Bilirubin**  
   - Measures bilirubin levels in the blood.  
   - *Normal Range*: 0.30 - 1.30 mg/dL  
   - *High Values May Mean*: Jaundice, hepatitis, or blocked bile ducts.  
   - *Low Values May Mean*: Anemia or low red blood cell production.

4. **Direct_Bilirubin**  
   - The part of bilirubin that helps spot liver issues.  
   - *Normal Range*: 0.10 - 0.50 mg/dL  
   - *High Values May Mean*: Liver disease or bile duct problems.  
   - *Low Values May Mean*: Rare metabolic issues (typically normal).

5. **Alkphos_Alkaline_Phosphotase**  
   - An enzyme tied to liver and bone health.  
   - *Normal Range*: 107 - 361.8 IU/L  
   - *High Values May Mean*: Liver blockage, tumors, or bone issues.  
   - *Low Values May Mean*: Malnutrition, hypothyroidism, or rare genetic conditions.

6. **Sgpt_Alamine_Aminotransferase**  
   - A liver enzyme that shows if the liver is damaged or inflamed (ALT).  
   - *Normal Range*: 10.0 - 68.0 IU/L  
   - *High Values May Mean*: Hepatitis, fatty liver, or cirrhosis.  
   - *Low Values May Mean*: Vitamin B6 deficiency or severe liver failure.

7. **Sgot_Aspartate_Aminotransferase**  
   - Another enzyme for checking liver health (AST).  
   - *Normal Range*: 13.0 - 52.8 IU/L  
   - *High Values May Mean*: Liver damage or even heart problems.  
   - *Low Values May Mean*: Advanced liver disease or malnutrition.

8. **Total_Protiens**  
   - Total protein in the blood (includes albumin and globulin).  
   - *Normal Range*: 6.0 - 8.0 gm/dL  
   - *High Values May Mean*: Dehydration or chronic inflammation.  
   - *Low Values May Mean*: Liver disease or malnutrition.

9. **ALB_Albumin**  
   - A protein the liver makes; low levels can signal trouble.  
   - *Normal Range*: 3.5 - 5.0 gm/dL  
   - *High Values May Mean*: Dehydration (rarely an issue).  
   - *Low Values May Mean*: Liver or kidney disease, or inflammation.

10. **A/G_Ratio_Albumin_and_Globulin_Ratio**  
    - Shows how the liver and kidneys are doing (Albumin/Globulin Ratio).  
    - *Normal Range*: 1.0 - 1.5   
    - *High Values May Mean*: Rare, but could indicate low globulin production.  
    - *Low Values May Mean*: Cirrhosis or kidney issues.

11. **Result (Target)**  
    - 1 = Liver disease, 0 = No liver disease.


## 5. Modeling  
We evaluated multiple machine learning models to determine the best-performing one based on **accuracy and recall**.

 1. Logistic Regression
- A statistical model used for binary classification.
- It predicts the probability of an event occurring based on input features.
- Uses the sigmoid function to map outputs between 0 and 1.

 2. Support Vector Machine (SVM)
- A supervised learning model that finds the optimal boundary (hyperplane) to separate data points.
- Works well with high-dimensional data and is used for classification and regression.
  
 3. Decision Tree
- A tree-based algorithm that splits data into branches based on feature conditions.
- Each node represents a decision, and each leaf represents an outcome.
- Useful for classification and regression tasks.

 4. Decision Tree
- A tree-based algorithm that splits data into branches based on feature conditions.
- Each node represents a decision, and each leaf represents an outcome.
- Useful for classification and regression tasks.

 5. K-Nearest Neighbors (KNN)
- A non-parametric algorithm that classifies data based on the majority class of its k-nearest neighbors.
- Works well for smaller datasets but is sensitive to irrelevant features and noise.

 6. Random Forest
- An ensemble learning method that combines multiple decision trees.
- Reduces overfitting and improves accuracy by averaging multiple predictions.
- Suitable for handling large datasets with non-linear relationships.

 7. XGBoost
- An optimized, fast implementation of Gradient Boosting.
- Uses parallel processing and regularization to improve performance.
- Frequently used in machine learning competitions and real-world applications.

 8. AdaBoost
- A boosting algorithm that assigns higher weights to misclassified samples to improve model accuracy.
- Combines weak learners to create a strong classifier.
- Used for image recognition, fraud detection, and medical diagnoses.

 9. Gradient Boosting
- A boosting algorithm that sequentially improves weak models by minimizing errors.
- Often used in structured data problems like finance and healthcare predictions.

## 6. Experimentation & Results  
To compare the performance of these models, we considered:
- **Accuracy**: How often the model makes the correct prediction,whether it's identifying a patient with liver disease or correctly saying a patient does not have liver disease.

- **Recall**: Recall focuses specifically on the positive,patients who have liver disease.In medical predictions, high recall is crucial to minimize missed diagnoses.

After evaluating all models, **XGBoost and Randomf Forest** demonstrated the highest recall along with strong accuracy, making it the most effective choice for predicting liver disease in this dataset.
