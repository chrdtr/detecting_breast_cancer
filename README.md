# Detecting breast cancer:

A dataset has been provided for analysis, containing different features which all have been measured during breast
cancer scans. The features have been computed from digitised images of a fine needle aspiration (FNA) of a breast mass.

The main goal is to make predictions whether or not potential features could lead to a diagnosis of breast cancer. To 
achieve this, it was decided to train and test different machine learning models on the data provided. After validation,
the model delivering the best predictions should be chosen. 

As the output variable is binary, we are facing a classification problem:
  
  y = M or 1 = malignant, or<br>
  y = B or 0 = benign

To make and compare predictions, the following machine learning models have been selected:

  1. Binary logistic regression (BLR)
  2. Support vector machines (SVM)
  3. Decision trees (DT)
  4. Random forests (RF)

These models have been applied as follows:

# 1. Binary logistic regression (BLR)
  ### Accuracy: 76% (v2: 63%)
  ### False negatives: 20 (v2: 2)
  
   - Data has been imported, sense-checked and statistically described
   - One redundant column was dropped and the regression model was fitted on the
     whole dataset to check for regression assumptions
   - VIF values indicated multicollinearity, as all variables showed VIF values > 10
   - Only the five varialbes with the lowest VIF factos were kept, leading to VIF < 10
   - As data was imbalanced, SMOTE was applied for balancing. y-variable then showed 249
     results for each diagnosis
   - The logistic regression model was fitted and then evaluated on the test data
   - It delivered an accuracy of <b>76.02%</b>. As the false negatives (20) matter the most in this specific
     case, it was tried to reduce them by altering the threshold for the prediction
   - This alternative delivered low false negatives (3), but came at the cost of further
     decreasing accuracy to 62.57%.

<b>In this context, the predictive power of the model is not sufficient.</b>

 # 2. Support vector machines (SVM)
   ### Accuracy: 98.25%
   ### False negatives: 2

   - Data has been imported, sense-checked and statistically described, one redundant column was dropped
   - As data was imbalanced, SMOTE was applied for balancing. y-variable then showed 249
     results for each diagnosis
   - The linear kernel SVM-model was fitted and then evaluated on the test data
   - It delivered an accuracy of <b>96.49%</b> and 3 false negative results.
   - To further improve the model, an alternative was created, scaling the data that
     has been used with the min-max-normalization method
   - It delivered an accuracy of <b>98.25%</b> and 2 false negative results.

<b>The updated SVM-model provides a high accuracy of 98.25% and only 2 FN predictions.</b>
 
 # 3. Decision trees (DT)
   ### Accuracy: 97.07%
   ### False negatives: 2

  - Data has been imported, sense-checked and statistically described, one redundant column was dropped
  - Data was imbalanced, but as decision tree models are robust to unequal y-distributions, it was
    decided to deploy the model without the further use of balancing methods
  - The model was fitted and delivered a <b>94.15%</b> accuracy on the test data.
  - In the next step the tree was pruned, resulting in a accuracy of <b>97.07%</b> and 2 false negative results.

<b>The decision tree model provides a high accuracy of 98.25% and only 2 FN predictions.</b>

 
 # 4. Random forests (RF)

- Data has been imported, sense-checked and statistically described, one redundant column was dropped
- Data was imbalanced, but just like decision trees, as random forests are robust to unequal y-distributions,
  it was decided to deploy the model without the further use of balancing methods
- The model was fitted and delivered a <b>97.08%</b> accuracy on the test data and 4 false negative results.
- To further improve the model, an alternative was created, scaling the data that
  has been used with the min-max-normalization method
- It delivered an accuracy of <b>98.25%</b> and 1 false negative results.

<b>The random forest model provides a high accuracy of 98.25% and only 1 FN predictions.</b>









The data was provided by London School of Economics and Political Science (LSE), as part of its Data Analytics Career Accelerator program.
