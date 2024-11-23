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

### Key Findings
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
- The confusion matrices show that the neural network correctly classified most instances of `DrugA` and `DrugC`. However, it misclassified some instances of `DrugB` and `DrugY`.

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
This project demonstrates the application of neural networks for a real-world classification problem, with a clear focus on data preparation, model performance evaluation, and potential improvements. The neural network approach outperformed logistic regression, especially in handling more complex relationships within the data.
