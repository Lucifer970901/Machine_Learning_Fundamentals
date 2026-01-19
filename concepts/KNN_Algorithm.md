# K-Nearest Neighbors (K-NN)

K-NN is a supervised machine learning algorithm used for both classification and regression. 

* It classifies new datapoints based on majority class (for classification) or (average value) for regression of its **K nearest neighbors** in the feature space.
* **Instance based learning** : It is a **lazy learner** (does not learn a model during training; computation happens at prediction time.)

## How K-NN works

1. **Choose the number of neighbors (K)**: Typically an odd number to avoid ties.
2. **Calculate distance** : the common metrics include:
    * Eucledean distance (most common)
    * Manhattan distance
    * Minkowski distance (generalized form)
3. **Find the K-Nearest neighbors** : Identify K closest data points
4. **Majority Voting (classification)** : Assign the class that appears most among neighbors
5. **Average (regression)** : Predict the average value of neighbors.

### Example (classification)

* New data point: Find its 3 nearest neighbors.
* Neighbors' classes: [Class A, Class A, Class B]
* Prediction: Class A (majority vote).

## Choosing the right K value

* Small K (e.g., K=1):
    * High variance (overfitting, sensitive to noise).
* Large K (e.g., K=20):
    * High bias (underfitting, smoother boundaries).