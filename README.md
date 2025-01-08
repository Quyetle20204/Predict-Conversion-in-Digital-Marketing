# Predict Conversion in Digital Marketing

This project employs machine learning techniques and the Python programming language to predict customer conversion likelihood. The CART algorithm is utilized in conjunction with the Gini index to identify the most critical attributes for data splitting. Additionally, Pruning techniques are applied to minimize overfitting, ensuring the model performs efficiently on real-world data.

## **Research Objectives:**

- **Provide an accurate prediction method**: Leverage the CART algorithm with the Gini index and Pruning techniques to develop a high-accuracy model for predicting customer conversion behavior.
- **Ensure ease of implementation and high applicability**: The prediction method is designed for practical application, delivering tangible value for businesses in the digital marketing domain.
- **Lay the foundation for effective and sustainable digital marketing strategies**: Offer a basis for developing digital marketing strategies that enhance efficiency and sustainability in the long term.

## **Key Components:**

- Initializing a decision tree model.
- Tuning the model using Cost Complexity Pruning.
- Tuning the model with Pre-Pruning techniques.
- Addressing class imbalance issues by employing the Balanced Bagging Classifier.
- Using performance metrics such as AUC-ROC, confusion matrices, and model summaries to evaluate model accuracy and effectiveness.

## **Data Limitations:**

- **Limited sample size:** The dataset contains 20 attributes with 8,000 observations. This relatively small sample size may result in overfitting, where the model performs well on training data but fails to generalize effectively to unseen data.
- **Class Imbalance:** The dataset exhibits an imbalanced class distribution, with 87.7% of observations representing conversions and 12.3% non-conversions. This imbalance may bias the predictive model toward the majority class, potentially reducing prediction accuracy and reliability.

## **Analysis Process**

- **Conversion Distribution:**

![image](https://github.com/user-attachments/assets/981a7d38-c6b5-46b7-80e0-32023636636e)


- **Descriptive Statistics:**

![image](https://github.com/user-attachments/assets/26b16f1a-803a-417a-8faa-a2d70c7279c5)


- **Correlation Matrix :**

![image](https://github.com/user-attachments/assets/e2a86357-b55a-48b0-8b57-4f869399edfd)


## **Modeling**

- **Initial Model:** The initial model used the `DecisionTreeClassifier` from Scikit-Learn. Parameters such as `criterion`, `class_weight`, `max_depth`, `min_samples_leaf`, and `min_samples_split` were set to default values.Classification results with default parameters:

![image](https://github.com/user-attachments/assets/a5b73d76-71f4-4bac-ab5b-2d74f34ed737)

***Comments:***  With default parameters, the model showed an **accuracy of 0.91 for label 1** but only **0.32 for label 0.** Similarly, the F1-score was **0.91 for label 1** and **0.33 for label 0.** This indicates overfitting as predictions heavily favor label 1, yielding skewed evaluation metrics.

![image](https://github.com/user-attachments/assets/0d26fecd-77c9-4cff-8796-3addd4821c60)

The AUC value of **0.62** indicates poor model performance.

## **Hyperparameter Tuning :**
   - **Cost Complexity Pruning** 
    
![image](https://github.com/user-attachments/assets/d6ef40b8-d14d-4808-ada6-c67ec45f0679)

    
  - **Pre-Pruning and Balanced Bagging Classifier:** 
    Pre-Pruning identified optimal parameters: `max_depth = 9`, `min_samples_split = 2`, and `min_samples_leaf = 4`. These parameters, combined with the `Balanced Bagging Classifier` from the Imbalanced-Learn library, improved performance.

![image](https://github.com/user-attachments/assets/f7adeaf5-5633-4663-a132-8a7e579b16a1)


## **Model Evaluation:**

After hyperparameter tuning, the model was evaluated using **Accuracy, F1-score, AUC, and ROC curve.**

- Accuracy: **82%**, indicating the model correctly predicted 82% of the 1,600 samples.
- F1-Score: For label 1, it reached **0.89**, showing good performance for the majority class. For label 0, it improved to **0.47**, a notable enhancement.
- AUC: **0.74**, reflecting better-than-random performance.

![image](https://github.com/user-attachments/assets/8f0abea4-0603-4556-8491-11b441e0f35a)

The improved AUC value highlights the model's ability to distinguish between classes effectively.
