# Analysis Report 

## Overview

The purpose of this analysis is to create a deep learning model to predict the success of charitable donations based on the features provided in the dataset from Alphabet Soup. The goal was to achieve an accuracy higher than 75% to effectively determine which organizations were more likely to receive funding. The analysis involved preprocessing the dataset, building multiple neural network models, and attempting different optimization strategies to improve model performance.

## Results

### Data Preprocessing

- **Target Variable**: The target variable for the model is `IS_SUCCESSFUL`, which indicates whether a given charitable donation was successful.
- **Features**: The features for the model include all other columns after removing the non-beneficial identifiers. These features represent different aspects of the charitable applications, including application types, classifications, and financial information.
- **Removed Variables**: The non-beneficial ID columns `EIN` and `NAME` were removed from the dataset, as they do not contribute any meaningful information for predicting the success of donations. Additionally, `ASK_AMT` was also dropped as it was determined to not improve model performance.

### Compiling, Training, and Evaluating the Model

- **Neural Network Model Design**:

    - **Trial 1**: The first model had 2 hidden layers with 128 and 64 neurons, respectively, using ReLU activation functions. This simple architecture was designed to capture basic relationships between features and targets.

    - **Trial 2**: The second model added more complexity with 4 hidden layers, having 128, 64, 32, and 16 neurons, respectively, all using ReLU activation functions. This deeper network aimed to capture more intricate relationships in the data.

    - **Trial 3**: The third model used 3 hidden layers with 128, 64, and 32 neurons, respectively, and switched the activation function from ReLU to Tanh. The Tanh activation function was used to test whether it could improve model performance by introducing a different non-linearity.
- **Model Performance**:

    - **Trial 1**: Loss: 0.5606, Accuracy: 72.57%

    - **Trial 2**: Loss: 0.5676, Accuracy: 72.51%

    - **Trial 3**: Loss: 0.5617, Accuracy: 72.45%

    - None of the trials were able to achieve the target model performance of 75% accuracy.
- **Steps to Increase Performance**:

    - **Adjust Input Data**: In Trial 1, additional columns such as `ASK_AMT` were removed to reduce noise in the data. Rare occurrences in categorical variables were replaced with 'Other' to simplify the feature space.

    - **Add More Layers**: In Trial 2, additional hidden layers were added to the model to increase its capacity and ability to learn complex relationships.

    - **Change Activation Functions**: In Trial 3, the activation function was changed from ReLU to Tanh in an attempt to capture different types of non-linearity.

### Summary

Overall, none of the trials were able to achieve the desired accuracy of 75%. The highest accuracy achieved was 72.57% in Trial 1. Adding more layers or changing activation functions did not lead to significant improvements, suggesting that further tuning or an entirely different approach might be necessary.

To solve this classification problem, I recommend exploring **ensemble methods**, such as **Random Forests** or **Gradient Boosting**. These models can often capture complex interactions between features more effectively without requiring extensive feature engineering or network tuning. Additionally, **XGBoost** is particularly well-suited for tabular data and may be more effective in handling the dataset's characteristics compared to a deep learning model. This approach could potentially yield better performance by leveraging multiple decision trees to improve prediction accuracy and robustness.