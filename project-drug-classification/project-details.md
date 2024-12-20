# Drug Type Classification Using Neural Networks

## Project Overview

This project involves the classification of drug types using neural networks, based on various patient data. The dataset used for this classification task is the `drugdataset.csv` file. The primary goal was to predict the drug type (DrugA, DrugB, DrugC, DrugX, DrugY) from a set of independent variables, including age, sex, blood pressure (BP), cholesterol levels, and the ratio of sodium to potassium in the blood (Na_to_K).

### Dataset Overview
- **Dependent Variable**: Drug type (`DrugA`, `DrugB`, `DrugC`, `DrugX`, `DrugY`)
- **Independent Variables**:
  - **Age** (Numerical): The age of the patient.
  - **Sex** (Categorical): 0 for Male, 1 for Female.
  - **BP** (Categorical): 0 for Normal, 1 for Low, 2 for High blood pressure.
  - **Cholesterol** (Categorical): 0 for Normal, 1 for High cholesterol.
  - **Na_to_K** (Numerical): The ratio of sodium to potassium in the blood.

### Model Overview - Neural Networks
- Neural networks are complex models capable of distinguishing between multi-class classifications. 
- The architecture used in this project is a generalized logistic regression model combined with hidden layers that add weights and biases to each input, enabling the model to learn non-linear patterns in the data.

### Descriptive Statistics
- **Gender Distribution**: 48% of patients are female, and 52% are male.
- **Age Distribution**: The ages of patients range from 15 to 74 years, with a mean age of 59 years.
- **Na_to_K Distribution**: The distribution of Na_to_K is right-skewed, indicating that the mean (16.08) is greater than the median (14.94).

## Model Performance Evaluation

### Precision, Recall, and F1-Score
- **Precision**: The model achieved high precision (97%) for drug types like `DrugA`, `DrugB`, and `DrugC`, with minimal false positives.
- **Recall**: The model identified all positive cases for `DrugA`, `DrugC`, and `DrugX`, with a notable lower recall for `DrugB` (67%).
- **F1-Score**: A perfect F1-score was achieved for `DrugA` and `DrugC`, meaning that the predictions for these drugs had no false positives or false negatives.
- **Accuracy**: The model achieved an overall accuracy of 95%, correctly classifying most of the data.

### Confusion Matrices

### Confusion Matrix

<div>
  <img src="https://github.com/tadelleg/tadelleg.github.io/blob/96ad20de8c7b9b446769a5085796ce62790006c4/images/confusion_matrix.png?raw=true" alt="Confusion Matrix" style="width:100%; height:auto;"/>
</div>

The confusion matrix above illustrates the performance of the neural network model across the different drug types.

- The matrix is normalized to show the proportion of correct and incorrect classifications.
- The ideal model would show all values along the diagonal, indicating perfect classification.

### Confusion Matrix Insights:
- The confusion matrices show that the neural network correctly classified most instances of `DrugA` and `DrugC`. However, it misclassified some instances of `DrugB` and `DrugY`.

## Model Architecture

#### Model Architecture Diagram

<div>
  <img src="https://github.com/tadelleg/tadelleg.github.io/blob/d7a66258b1dcaf3a49e4f7d5c676ead3fc733846/images/model_architecture.png?raw=true" alt="Model Architecture" style="width:100%; height:auto;"/>
</div>


### Overview
The neural network model used in this project consists of several layers, including an input layer, hidden layers, and an output layer. The input layer receives the features of the dataset (age, sex, BP, cholesterol, and Na_to_K). The hidden layers learn the patterns within the data, while the output layer provides a classification into one of the five drug types.

1. **Input Layer**: Contains 5 neurons corresponding to the 5 input features (age, sex, BP, cholesterol, Na_to_K).
2. **Hidden Layer 1**: 64 neurons, using the ReLU activation function, which allows the network to learn non-linear patterns.
3. **Hidden Layer 2**: 32 neurons, also using ReLU activation.
4. **Output Layer**: 5 neurons, each representing one of the five drug types (DrugA, DrugB, DrugC, DrugX, DrugY), with softmax activation to ensure the output is a probability distribution over the drug classes.

### Summary
- The neural network achieves exceptional classification accuracy for all drug classes, with most drugs being classified perfectly (AUC = 1). Even `DrugY`, the worst-performing class, has an AUC of 0.99, indicating excellent performance overall.

### Conclusion
The neural network architecture is suitable for multi-class classification tasks and has been designed to balance model complexity with performance. The high accuracy and AUC scores indicate that the model is effectively capturing the underlying relationships between the features and drug types.


## ROC Curve Analysis

### ROC Curve Image

<div>
  <img src="https://github.com/tadelleg/tadelleg.github.io/blob/d7a66258b1dcaf3a49e4f7d5c676ead3fc733846/images/roc_curve.png?raw=true" alt="ROC Curve" style="width:100%; height:auto;"/>
</div>

### Analysis of the ROC Curve

The **ROC curve** for the model provides insight into how well the classifier distinguishes between different drug types. The curve plots the **True Positive Rate (TPR)** against the **False Positive Rate (FPR)** for each possible threshold. 

1. **Axes**:
   - **X-axis**: False Positive Rate (FPR), the proportion of negatives incorrectly classified as positives.
   - **Y-axis**: True Positive Rate (TPR), the proportion of positives correctly identified.

2. **Curves and Areas**:
   - The ROC curves for `DrugA`, `DrugB`, `DrugC`, `DrugX`, and `DrugY` demonstrate how well the model distinguishes between each class.
   - **AUC** values:
     - `DrugA`, `DrugB`, `DrugC`, and `DrugX`: AUC = 1.00 (perfect discrimination).
     - `DrugY`: AUC = 0.99 (near-perfect discrimination).
     - A random guess baseline is shown with AUC = 0.5.

3. **Perfect Models**:
   - The near-perfect vertical jumps at the left (close to FPR = 0, TPR = 1) indicate excellent performance.
   - `DrugA`, `DrugB`, `DrugC`, and `DrugX` have perfect sensitivity and specificity.

4. **Minor Imperfection for DrugY**:
   - `DrugY` shows a slight deviation with AUC = 0.99, indicating a small amount of misclassification.

### Comparison with Logistic Regression

| Metric                    | Neural Networks | Logistic Regression | Observation                        |
|---------------------------|-----------------|---------------------|------------------------------------|
| **Accuracy**               | 95%             | 93%                 | Neural networks have higher accuracy |
| **Macro Avg Precision**    | 97%             | 96%                 | Neural networks are slightly more precise |
| **Macro Avg Recall**       | 92%             | 90%                 | Neural networks have better recall |
| **Macro Avg F1-Score**     | 94%             | 93%                 | Neural networks perform slightly better overall |
| **Weighted Avg F1-Score**  | 95%             | 93%                 | Even weighted, neural networks have fewer false positives/negatives |

### Evaluation – Limitations and Improvements

#### Limitation 1: **Overfitting with Small Datasets**  
- **Improvement**: Increase training data size, possibly by collecting more real-world data, transforming the data, or using similar public datasets.

#### Limitation 2: **Non-optimal Default Parameters**  
- **Improvement**: Hyperparameter tuning to adjust the number of hidden layers, neurons, and activation functions for better model performance.

#### Limitation 3: **Irrelevant Feature Scaling**  
- **Improvement**: Apply feature scaling or engineering, using domain knowledge to combine and transform certain variables for better relevance in predictions.

## Conclusion – Key Takeaways
- **Algorithm Choice**: Neural networks are better suited for complex problems and can effectively capture non-linear relationships in the data. However, they may require additional improvements, such as data augmentation and hyperparameter tuning.
- **Logistic Regression**: Ideal for simpler, easier-to-interpret problems, but struggles with small classes, as seen in the misclassification of `DrugB`.
- **Performance Summary**: 
  - **Neural Networks**: Superior accuracy, recall, and F1-scores for most drug types, with minimal false positives and false negatives.
  - **Logistic Regression**: Performed well overall but struggled with smaller classes like `DrugB`.

## Suggestions for Further Work
- Continue to experiment with model architectures, including deep neural networks.
- Apply advanced feature engineering techniques to improve model performance, particularly in predicting rare classes.
- Consider using ensemble methods or hybrid models to improve accuracy for the misclassified drug types.

## Additional Resources
- **Dataset**: [drugdataset.csv](./drugdataset.csv)

## Final Thoughts
This project demonstrates the application of neural networks for drug classification, with outstanding model performance and promising results for future improvements.
