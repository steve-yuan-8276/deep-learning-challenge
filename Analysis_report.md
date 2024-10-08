# Analysis Report 

## Overview

The purpose of this analysis is to develop a deep learning model that predicts the success of charitable donations based on the features provided in the dataset from Alphabet Soup. The goal is to achieve an accuracy of 75% or higher, allowing the model to effectively determine which organizations are more likely to receive funding. This analysis includes data preprocessing, the construction and evaluation of multiple neural network models, and attempts to optimize model performance through various strategies.


## Q&A

This project created two Jupyter Notebooks, including a basic script and an optimized script, aimed at answering the following questions:

### Question 1: What variable(s) are the target(s) for your model?

**Answer**: The target variable for the model is `IS_SUCCESSFUL`, which indicates whether a charitable donation was successful. It is a binary classification task where `1` represents a successful donation and `0` represents an unsuccessful one.

* * *

### Question 2: What variable(s) are the features for your model?

**Answer**: The feature variables for the model include all the other columns in the dataset after removing the identifier columns. These features are:

- `APPLICATION_TYPE`
- `AFFILIATION`
- `CLASSIFICATION`
- `USE_CASE`
- `ORGANIZATION`
- `INCOME_AMT`
- `ASK_AMT`
- `STATUS`
- `SPECIAL_CONSIDERATIONS`

These features represent various categorical and numerical data points that are used to predict the success of a donation.

* * *

### Question 3: What variable(s) should be removed from the input data because they are neither targets nor features?

**Answer**: The variables that were removed from the input data are:

- `EIN`: An identifier for the organization, which is non-beneficial for prediction purposes.
- `NAME`: Another identifier, which does not contribute to the prediction task.
- `ASK_AMT`: This was removed during some trials, as it did not provide value in improving the model's performance and may have added noise to the data.
* * *

### Question 4: How many neurons, layers, and activation functions did you select for your neural network model, and why?

**Answer**:

- **Trial 1**: The model had 2 hidden layers with 128 neurons in the first layer and 64 neurons in the second layer, using ReLU activation functions. This setup was chosen for its simplicity and ability to capture basic relationships.
- **Trial 2**: The model was expanded to 4 hidden layers with 128, 64, 32, and 16 neurons, respectively, all using ReLU activation functions. The increased complexity aimed to capture more intricate relationships.
- **Trial 3**: The model had 3 hidden layers with 128, 64, and 32 neurons, and the activation function was switched to Tanh. This was to test whether a different activation function would improve learning and performance.
* * *

### Question 5: Were you able to achieve the target model performance?

**Answer**: No, the target performance of 75% accuracy was not achieved in any of the trials. The highest accuracy achieved was **72.57%** in Trial 1, with additional complexity in Trials 2 and 3 not significantly improving performance.
* * *

### Question 6: What steps did you take in your attempts to increase model performance?

**Answer**:

- **Adjusting Input Data**: In Trial 1, columns such as `ASK_AMT` were removed to reduce noise in the data. Rare categories in some features were grouped into a new category, `Other`, to reduce the model's need to learn from sparse categories.
- **Adding More Layers**: In Trial 2, the model's depth was increased by adding more hidden layers to capture more complex relationships between the features and the target.
- **Changing Activation Functions**: In Trial 3, the activation function was changed from ReLU to Tanh, which introduces different non-linearities that might help the model learn better representations of the data.



### Summary

Overall, none of the trials were able to achieve the desired accuracy of 75%. The highest accuracy achieved was 72.57% in Trial 1. Adding more layers or changing activation functions did not lead to significant improvements, suggesting that further tuning or an entirely different approach might be necessary.

To solve this classification problem, I recommend exploring **ensemble methods**, such as **Random Forests** or **Gradient Boosting**. These models can often capture complex interactions between features more effectively without requiring extensive feature engineering or network tuning. Additionally, **XGBoost** is particularly well-suited for tabular data and may be more effective in handling the dataset's characteristics compared to a deep learning model. This approach could potentially yield better performance by leveraging multiple decision trees to improve prediction accuracy and robustness.