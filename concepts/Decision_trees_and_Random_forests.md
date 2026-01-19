# Decision Trees and Random forests

## Decision Trees

A decision tree is a supervised machine learning algorithm used for both classification and regression. it works by recursively splitting the dataset into subsets based on most significant feature at each step.

### Key concepts

* **Root node** : The topmpst decision node
* **Internal nodes** : Decision nodes that split the data
* **leaf nodes** : terminal nodes that give final prediction
* **Spliiting criteria** : 
    * **classification** : Gini impurity or entropy (Information Gain)

    *  * **Gini impurity** : It tells how pure the dataset is.It tells you the probability that a randomly chosen element from the set would be incorrectly labeled if you randomly labeled it according to the distribution of labels in that set.

        In simpler terms: Lower impurity means the group is more uniform.

        * **Entropy** : measures the amount of uncertainty or randomness in a dataset
            * If a set is pure (all items are the same), Entropy is 0.

            * If a set is perfectly mixed (50/50 split), Entropy is 1.
            The Formula
            $$H(S) = - \sum_{i=1}^{n} p_i \log_2(p_i)$$

            Where 8$p_i$ is the probability of class 9$i$.10 The negative sign ensures the result is positive, and the base-2 logarithm means we measure information in "bits."

        * **Information gain** is the actual metric used to pick the best feature for a split.12 It measures how much the entropy decreases after we split the data based on a specific attribute.
        
        The Formula $$IG(S, A) = H(S) - \sum_{v \in \text{Values}(A)} \frac{|S_v|}{|S|} H(S_v)$$
        In simple terms Information Gain = (Entropy Before) - (Weighted Entropy After the Split)   

    * **Regression** : Mean squared error (MSE) or variance reduction
        Variance measures how spread out the values are in a node.

        * High Variance: The numbers in the node are very different (e.g., [10, 500, 1000]).

        * Low Variance: The numbers are very similar (e.g., [102, 105, 101]).

        The goal of a Regression Tree is to create "pure" leaf nodes where the numbers are as close to each other as possible.


### How it works

1. **Select the best feature**: Choose the feature that best splits the data (maximize information gain, minimie the impurity)
2. **Split the data**: Divide the dataset into subsets based on selected features
3. **Repeat**: Continue splitting until a stopping condition is met (max depth, minimum samples per leaf etc.)
4. **Prediction**: New data points traverse the tree from root to leaf, where majority class (Classification) or average value (regression) is predicted.


### Advantages

* Easy to interpret
* Handles both numerical and categorical data
* No need for feature scaling

### Disadvantages

* Prone to overfitting (high variance)
* Sensitive to small changes in data (unstable)

---

## Random forests

Random forest is an ensemble learning method that builds multiple decision trees and combines their predictions to improve accuracy and reduce overfitting.

### Key concepts
* **Ensemble method** : Uses **bagging (bootstrap Aggregation)** to train multiple trees on different subsets of data
* **Feature randomness** : Each tree considers a random subset of features at each split (reduces corelation between trees)
* **Majority voting (Classification) / Averaging (Regression)** : Final prediction is based on consensus of all trees.

### How it works

1. **Bootstrap Sampling** : Randomly select subsets of data (with replacement) to train each tree
2. **Random feature selection** : At each split only a random subset of features is considered
3. **Aggregation Predictions** : 
    * For classification, the majority vote wins.
    * For regression the average of all tree predictions is taken.

### Advantages

* Reduces overfitting compared to a single decision tree
* Handles high dimensional data well.
* Provides feature importance scores

### Disadvantages

* Less interpretable that single decision tree.
* Slower training and prediction time due to multiple trees.

---

### Key Differences

| Feature | Decision Tree | Random Forest |
| :--- | :--- | :--- |
| Model Type | Single tree | Ensemble of trees |
| Overfitting | High risk | Reduced (due to averaging) |
| Stability | Sensitive to data changes | More stable |
| Interpretability | High | Lower (black-box) |
| Performance | Lower accuracy | Higher accuracy |

### When to use?

* Decision Tree: When interpretability is crucial and dataset is small. 
* Random Forest: When higher accuracy is needed and computational cost is acceptable.