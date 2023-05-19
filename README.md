# CrossVal-BiasVariance-R

This repository contains two statistical explorations implemented in R. The explorations focus on cross-validation and bias-variance tradeoff. Below, you'll find a description of each part along with the steps to reproduce the experiments.

## Part A: Cross Validation

In this part, we implement cross-validation as a method to identify the optimal degree (d) for a regression problem. The goal is to estimate the generalization error by splitting the dataset into training and test sets and performing regression using the poly function in R.

### Steps to reproduce:
1. **Dataset Construction**: We construct the dataset as follows:
   - Sample a vector X ∈ R^n where each Xi ∈ U [0, 1]. Each sample point Xi is sampled from the uniform distribution.
   - Construct Y from X using the equation: Y = 3 × X^5 + 2 × X^2 + ε, where ε ∈ R^n. Each εi is sampled independently from the N(0, 0.5) normal distribution. Choose n = 10000.
2. **Train-Test Split**: Split the dataset into an 80% training set and a 20% test set. Randomize the data using a seed to replicate the results.
3. **Cross Validation**: Split the training set into 5 folds and perform cross-validation to choose the optimal degree (d). Implement the Mean Squared Error (MSE) error function to estimate the error on each fold. Calculate the CV error as the average MSE across all five folds. Plot the CV error as a function of d for d ∈ [1, 2, ..., 10]. Note that you should code the cross-validation function from scratch without using any packages.
4. **Model Performance**: Use the entire training set to train models with different degrees (d). Compute the performance of the models on the test set by calculating the test MSE and training MSE as a function of d. Plot the test MSE and training MSE as a function of d and provide observations and comments on the results.

## Part B: Bias-Variance Tradeoff

This part explores the bias-variance tradeoff as model complexity increases. We use the entire training set to train models of the form Y ∼ poly(X). The goal is to compare the bias and variance of 10 different models for degrees d ∈ [1, 2, ..., 10] and predict the output at a new test point x = 1.01.

### Steps to reproduce:
1. **Training Dataset Generation**: Generate 1000 training datasets using the same function form as in Part A but with n = 100. For each simulated training dataset, train 10 different models for degrees d ∈ [1, ..., 10]. Store and compute the prediction for x = 1.01.
2. **Bias and Variance Calculation**: Calculate the bias and variance of the prediction value for each model. Plot the bias and variance as a function of d.
3. **: Consider the following cases and analyze their impact on bias and variance:
   - (a) Plot the bias and variance when sampling from Xi ∈ U [0, 10] instead of U [0, 1].
   - (b) Plot the bias and variance when using the test point x = -0.5 instead of x = 1.01.
   Analyze the plots and discuss the implications of the observed trends. Can we mitigate any of the issues? Provide explanations and insights.

## Conclusion

By performing these statistical explorations, we gain insights into cross-validation for model selection and the bias-variance tradeoff. The results obtained from these experiments help us understand the behavior of different models and their performance under various conditions
