# CrossVal-BiasVariance-R

In this repository, I have implemented two statistical explorations using R to investigate cross-validation and the bias-variance tradeoff. Here, I will provide a brief overview of each part along with the steps to reproduce the experiments.

## Part A: Cross Validation

In this part, I implemented cross-validation as a method to identify the optimal degree (d) for a regression problem. The goal was to estimate the generalization error by splitting the dataset into training and test sets and performing regression using the poly function in R.

###To reproduce the experiment, follow these steps:

1. Dataset Construction: Construct the dataset by sampling a vector X ∈ R^n where each Xi ∈ U [0, 1]. Then, construct Y from X using the equation Y = 3 × X^5 + 2 × X^2 + ε, where ε ∈ R^n and each εi is sampled independently from the N(0, 0.5) normal distribution. Choose n = 10000.
2. Train-Test Split: Randomly split the dataset into an 80% training set and a 20% test set. Use a seed value for replicability.
3. Cross Validation: Split the training set into 5 folds and perform cross-validation to choose the optimal degree (d). Implement the Mean Squared Error (MSE) error function to estimate the error on each fold. Calculate the CV error as the average MSE across all five folds. Plot the CV error as a function of d for d ∈ [1, 2, ..., 10]. Note that you should code the cross-validation function from scratch without using any packages.
4. Model Performance: Train models with different degrees (d) using the entire training set. Compute the performance of the models on the test set by calculating the test MSE and training MSE as a function of d. Plot the test MSE and training MSE as a function of d and provide observations and comments on the results.

## Part B: Bias-Variance Tradeoff

In this part, I explored the bias-variance tradeoff as the model complexity increases. I used the entire training set to train models of the form Y ∼ poly(X). The objective was to compare the bias and variance of 10 different models for degrees d ∈ [1, 2, ..., 10] and predict the output at a new test point x = 1.01.

###To reproduce the experiment, follow these steps:

1. Training Dataset Generation: Generate 1000 training datasets using the same function form as in Part A, but with n = 100. For each simulated training dataset, train 10 different models for degrees d ∈ [1, ..., 10]. Store and compute the prediction for x = 1.01.
2. Bias and Variance Calculation: Calculate the bias and variance of the prediction value for each model. Plot the bias and variance as a function of d.
3. Exploring Different Cases: Explore the impact on bias and variance under the following cases:
(a) Plot the bias and variance when sampling from Xi ∈ U [0, 10] instead of U [0, 1].
(b) Plot the bias and variance when using the test point x = -0.5 instead of x = 1.01.
Analyze the plots and discuss the implications of the observed trends.

## Conclusion

By conducting these statistical explorations, I gained insights into cross-validation for model selection and the bias-variance tradeoff. The obtained results help understand the behavior and performance of different models under various conditions.
