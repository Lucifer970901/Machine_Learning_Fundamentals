# Hyperparameter Tuning

Hyperparameter tuning is the process of finding the optimal combination of hyperparameters for a machine learning model. 

A hyperparameter search consists of four key components:

1. **Hyperparameter space**: This defines the range of possible values for each hyperparameter you want to tune. For example, for a random forest, this might include the number of trees, maximum depth, minimum samples per leaf, etc. 

2. **Sampling method**: This determines how candidate hyperparameter combinations are selected from the space. Common approaches include: 
    * **Grid search** (exhaustively tries all combinations)
    * **Random search** (randomly samples combinations) 
    * **Bayesian optimization** (intelligently selects promising combinations based on previous results) 

3. **Cross-validation scheme**: This is how you evaluate each candidate hyperparameter set. Typically k-fold cross-validation is used, where the data is split into k parts, with each part serving as the test set once while the others are used for training. 

4. **Performance metric**: This is what you're trying to optimize (either minimize or maximize). The choice depends on your problem - accuracy, precision, recall, RMSE, etc.

## Parameters vs Hyperparameters

Parameters are:

* The internal variables of a model that the algorithm learns during training.
* Examples: weights in a neural network, coefficients in linear regression, split joints in decision trees.
* They're optimized automatically as part of the training process.

Hyperparameters are:
 
* Settings you choose before training begins 
*  They control how the model learns its parameters 
* Examples: number of trees in a random forest, learning rate in gradient boosting, Tree depth in decision trees , Regularization strength.

Here shows the key differences

| **Feature** | **Parameters** | **Hyperparameters** |
| :--- | :--- | :--- |
| Set by | Learning algorithm | Data scientist |
| Learned from | Training data | Not learned - set before training |
| Purpose | Make predictions | Control learning process |
 | Adjusted via | Optimization (e.g., gradient descent) | Manual tuning or automated search |

Hyperparameters are the "knobs" and "dials" we adjust before training a model. 
* They can control: How the model learns , The model's structure , The training process itself.
* Key characteristics:  Not learned from data (set manually) , Control model capacity (complexity/flexibility) , Affect performance significantly

---

## Hyperparameters in Random Forests and GBMs

For tree-based models like Random Forests and Gradient Boosting Machines (GBMs), key hyperparameters include:

1. **Number of trees**: How many individual decision trees to build 
2. **Depth of trees**: How many levels each tree can have 
3. **Learning rate (GBMs only)**: How quickly the model adapts (smaller = slower but potentially more accurate) 
4. **Split quality metric**: How to measure the best way to split data at each node 
5. **Features per node**: How many features to consider for each split 
6. **Minimum samples to split**: The smallest number of data points needed to create a new split

## Why Hyperparameter Tuning Matters

The different hyperparameter combinations can lead to different model performance (measured by MSE, RMSE  - error metrics).

1. **Performance Impact**: 
    *  Good hyperparameters → Better model accuracy 
    *  Bad hyperparameters → Poor performance 
2. **Dataset Dependence**: 
    * Optimal settings vary by dataset 
    * Must be tuned for each new problem 
3. **Overfitting Control**: 
    * Help balance bias-variance tradeoff 
    * Example: Limiting tree depth prevents overly complex trees

## Hyperparameter Optimization

This is the process of finding the best hyperparameters for your specific dataset. Key points:

1. There's no formula - we have to test different combinations 
2. We evaluate each combination by training a model and checking its performance 
3. The goal is to minimize generalization error (how well the model works on new data)

## Challenges in Hyperparameter Tuning 

1. **No direct solution**: We can't calculate the best values mathematically 
2. **Trial and error**: We must test many combinations to find good ones 
3. **Trade-offs**:
    * More combinations tested = better chance of finding optimal settings 
    * But more combinations = more computation time and resources

##  Practical Implications

When tuning hyperparameters:

* Start with reasonable default values 
* Use methods like grid search or random search to explore combinations 
* Balance between thoroughness (testing many options) and computational cost 
* Remember that sometimes several different hyperparameter sets can work well

## Main Approaches to Hyperparameter Tuning

There are several strategies to find the best hyperparameters:

1. **Manual Search**: You manually try different combinations based on experience/intuition 
2. **Grid Search**: Systematically tries every combination in a predefined grid 
3. **Random Searc**h: Randomly samples combinations from predefined ranges 
4. **Bayesian Optimization**: Uses past results to intelligently select promising combinations 
5. **Other Methods**: Genetic algorithms, gradient-based optimization, etc.

## Understanding the Response Surface

The "response surface" is like a landscape showing how performance changes with different hyperparameters:

* Imagine each hyperparameter combination as a location on a map 
* The height at that point represents model performance (error or accuracy) 
* Our goal is to find the lowest point (for error) or highest point (for accuracy)

The mathematical formulas show we're trying to find hyperparameters (λ) that minimize our loss function (Ψ).

## Practical Example with Random Forests

* Defining a Random Forest with certain hyperparameters 
* Creating a parameter grid to search through (n_estimators and max_depth) 
* Using GridSearchCV to find the best combination 
* The search evaluates each combination using cross-validation

## Low Effective Dimension Concept

This is an important insight about hyperparameters:

* Not all hyperparameters affect performance equally 
* Only a few "active" hyperparameters really matter (the effective dimensions) 
* Most have little impact on model performance 
* This explains why random search can work well - you don't need to test every combination of unimportant parameters.

## Parameters and Hyperparameters by model type

### Linear regression

* **Parameters**: β coefficients (β₀, β₁, β₂, etc.) 
* **Equation**: Y = β₀ + β₁X₁ + β₂X₂ + ... + ε 
* **Loss function**: RSS (Residual Sum of Squares)
* **Vanilla (basic) version**: No hyperparameters
* **Regularized versions**: 
    * λ (lambda): Controls regularization strength 
    * Ridge Regression: λΣβⱼ² (L2 penalty) 
    * Lasso Regression: λΣ|βⱼ| (L1 penalty) 
    * Elastic Net: Combination of L1 and L2

### Decision Trees

**Parameters**:
*   * Which features to split on 
    * Split thresholds 
    * Tree structure

**Hyperparameters**: 
*   * **Max depth**: How deep the tree can grow 
    * **Min samples split**: Minimum data points needed to split a node 
    * **Split criterion**: Gini impurity or entropy 
    * **Max features**: Number of features to consider at each split

### Random Forests & Gradient Boosted Machines (GBMs)

**Hyperparameters**
*   * **Number of trees/estimators**
    * **Max depth** (per tree) 
    * **Learning rate** (GBMs only): How quickly the model adapts 
    * **Subsample ratio**: Fraction of data used for each tree


### Neural Networks

* **Parameters**: 
*   * All the connection weights between neurons 
    * Bias terms 
* **Hyperparameters**: 
    * Number of layers 
    * Number of neurons per layer 
    * Learning rate 
    * Activation functions
    * Batch size
    * Dropout rate
    * Weight decay

### other models

the hyper parameters for other models includes:

* **k-Nearest Neighbors**: Number of neighbors (k)
* **Support Vector Machines**: 
    * Kernel type (linear, RBF, polynomial) 
    * Regularization parameter (C)