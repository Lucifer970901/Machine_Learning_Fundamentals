# Machine Learning Fundamentals.

## 1.Introduction to Machine learning

### What is Machine learning

* Machine learning (ML) is a subset of Artificial Intelligence that enables the system to learn from the data and improve their performance without being explicitly programmed

* Instead of hardcoded rules. we train the models on the data to make predictions and decisions

### Why Machine learning

* **Automation**: ML automates decision making (e.g. spam detection, recommendation systems.)

* **Handling complex data**: Find patterns in large datasets, where analysis is impossible.

* **Adaptability**: Model improves overtime with new data.

### Example applications

* **Supervised Learning**: Email spam detection, House price predictions.

* **Unsupervised Learning**: Customer Segmentaion, Anlomaly detection.

* **Reinforcement Learning**: Self driving cars, Game playing AI (AlphaGO)

## 2.Types of Machine Learning

### 1. Supervised Learning (Learning from Labeled Data)

* The model learns from input-output pairs (X→y).

* **Goal**: Predict the output for new, unseen data.

* **Types**:

    * **Regression** (Continuous Output): Predict house prices, stock prices.

    * **Classification** (Discrete Output): Spam vs. not spam, image recognition.

### 2. Unsupervised Learning (Finding Patterns in Unlabeled Data)

* The model learns hidden structures from data without labels.

* **Goal**: Discover patterns, groupings, or anomalies.

* **Types**:

    * **Clustering**: Grouping similar customers (e.g., K-Means).

    * **Dimensionality Reduction**: Reducing features (e.g., PCA).

    * **Anomaly Detection**: Fraud detection.

### 3. Reinforcement Learning (Learning by Trial & Error)

* The model learns by interacting with an environment and receiving rewards/punishments.

* **Goal**: Maximize cumulative reward (e.g., game AI, robotics).

### 4. Semi-Supervised & Self-Supervised Learning (Brief Mention)

* Uses a mix of labeled and unlabeled data (common in real-world scenarios).

## 3. How Machine Learning Works

### Key Steps in ML:

1. **Data Collection**: Gather relevant data (structured/tabular, images, text).

2. **Data Preprocessing**: Clean, normalize, handle missing values (using Pandas, NumPy).

3. **Feature Engineering**: Select/extract meaningful features (e.g., converting text to numbers).

4. **Model Selection**: Choose an algorithm (Linear Regression, Decision Trees, Neural Networks).

5. **Training**: Fit the model on training data (adjusting weights to minimize error).

6. **Evaluation**: Test on unseen data (using metrics like accuracy, MSE).

7. **Deployment**: Use the model in real-world applications.

### Example Workflow (House Price Prediction):

* Input Features (X): Size, location, bedrooms.

* Output (y): Price.

* Model: Linear Regression → Predicts price for new houses.

## 4. Common Machine Learning Algorithms

### Supervised:

* **Regression**: Linear Regression, Decision Trees.

* **Classification**: Logistic Regression, SVM, Random Forest.

### Unsupervised:

* **Clustering**: K-Means, DBSCAN.

* **Dimensionality Reduction**: PCA, t-SNE.

### Deep Learning (Brief Intro):

* Neural Networks for complex tasks (image, speech recognition).