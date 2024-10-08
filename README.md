# Deep Learning Challenge: Alphabet Soup Charity Funding Predictor

## Background

Alphabet Soup, a nonprofit foundation, seeks a tool that can help it select applicants for funding with the best chance of success in their ventures. With the data provided by Alphabet Soup, which contains information on over 34,000 organizations that have received funding in the past, our goal is to create a machine learning model capable of predicting whether an applicant will be successful if funded. This tool can help Alphabet Soup make informed decisions and maximize the impact of their funding.

## Project Overview

In this project, we use machine learning techniques, specifically neural networks, to create a binary classifier that predicts the likelihood of an applicant's success based on the features in the dataset.

- **Target Variable**: `IS_SUCCESSFUL`
- **Features**: All columns except `EIN`, `NAME`, and `IS_SUCCESSFUL`.
- **Removed Variables**: `EIN` and `NAME` as they do not contribute to the prediction task.


## Key Files

- `AlphabetSoupCharity_Optimization.ipynb`: The notebook containing the optimized versions of the model.
- `deep-learning-challenge.ipynb`: The notebook for initial data preprocessing, model training, and evaluation.
- `Outputs/`: Directory containing the HDF5 files for different models.

    - `AlphabetSoupCharity_Trial1.h5`, `AlphabetSoupCharity_Trial2.h5`, `AlphabetSoupCharity_Trial3.h5`: Saved models from each trial.

    - `trained_application_model.h5`: Initial trained model.
- `Analysis_report.md`
- `README.md`


## Projects Steps：

### Part 1: Initial attempt:

1. **Data Preprocessing**: Prepare and clean the dataset to ensure the model receives well-structured input data.

2. **Compile, Train, and Evaluate the Model**: Build, compile, train, and evaluate a neural network model using TensorFlow.

3. **Model Optimization**: Make multiple attempts to optimize the neural network to achieve a target accuracy above 75%.

4. **Model Analysis**: Evaluate and report on the overall performance of the deep learning model.



### Part 2: Optimize the Model

1. **Adjust Model Parameters**: Optimize the model using at least three of the following techniques:

    - **Drop or Adjust Columns**: Simplified the feature set by removing additional columns like `ASK_AMT` to reduce noise in the data.

    - **Add More Layers**: Increased the model capacity by adding more hidden layers to better capture complex patterns.
    
    - **Change Activation Functions**: Experimented with different activation functions, switching from ReLU to Tanh, to capture different types of non-linearity.

2. **Evaluate and Save**: Evaluate the optimized model and save it as `AlphabetSoupCharity_Optimization_Trial 1-3`,please check the outputs folders for details.



## Performance Results & Recommendations

    - None of the models achieved the target accuracy of 75%, with the highest accuracy being 72.57%.

    - Optimizing the model by adding more complexity did not significantly improve results.

Given the limited success of deep learning for this problem, a different approach may be more effective. **Ensemble methods**, such as **Random Forest** or **XGBoost**, are well-suited for tabular data and could yield better results by capturing more nuanced relationships between features and reducing overfitting.