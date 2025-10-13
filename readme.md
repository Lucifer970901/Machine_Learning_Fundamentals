# 🤖 Machine Learning Fundamentals & Concepts

This repository contains my structured learning notes, theoretical breakdowns, and practical, scikit-learn-focused Python examples for core Machine Learning algorithms and foundational concepts.

## 🎯 Learning Goals

This repository is designed to document mastery of the theoretical underpinnings and practical implementation of essential supervised learning models and validation techniques.

| Area | Goal |
| :--- | :--- |
| **Model Theory** | Deep understanding of the mechanism, advantages, and limitations of each core algorithm. |
| **Model Evaluation** | Proficiency in selecting appropriate metrics and using robust **cross-validation** techniques. |
| **ML Engineering** | Systematic approach to **hyperparameter tuning** and using modular, production-ready code structures. |

---

## 📂 Repository Structure

The content is organized into three main categories: theoretical notes, algorithm deep dives, and executable examples.

| Directory | Content Type | Focus |
| :--- | :--- | :--- |
| **`concepts/`** | Core ML Foundational Principles (e.g., bias/variance, metrics). | **Theory** |
| **`algorithms/`** | Detailed notes on specific model mechanics and mathematics. | **Theory & Math** |
| **`examples/`** | Executable Python scripts and Jupyter Notebooks using **scikit-learn**. | **Practical Application** |

---

## 📚 Core Topics Covered

### 1. Model Algorithms (The "Learners")

| Algorithm | Status | Primary File Location(s) | Key Concepts |
| :--- | :--- | :--- | :--- |
| **Logistic Regression** | ✅ Complete | `algorithms/Logistic_Regression.md` | Sigmoid Function, Cost Function, Classification Boundary. |
| **K-Nearest Neighbors (KNN)** | ✅ Complete | `algorithms/K_Nearest_Neighbors.md` | Distance Metrics (Euclidean), The role of *k*, Lazy Learning. |
| **Decision Trees** | ✅ Complete | `algorithms/Decision_Trees.md` | Impurity (Gini, Entropy), Splitting, Overfitting. |
| **Random Forest** | ✅ Complete | `algorithms/Random_Forest.md` | Ensemble Methods, Bagging, Feature Randomness, Bias-Variance Tradeoff. |

### 2. Validation & Tuning (The "Process")

| Concept | Status | Primary File Location(s) | Focus |
| :--- | :--- | :--- | :--- |
| **Cross-Validation** | ✅ Complete | `concepts/Cross_Validation.md` | K-Fold, Stratified K-Fold, preventing data leakage. |
| **Hyperparameters** | ✅ Complete | `concepts/Model_Tuning.md` | Distinction from parameters, Grid Search, Random Search. |

### 3. Evaluation (The "Metrics")

| Metric Group | Status | Primary File Location(s) | Key Metrics |
| :--- | :--- | :--- | :--- |
| **scikit-learn Metrics** | ✅ Complete | `concepts/Evaluation_Metrics.md` | Precision, Recall, F1-Score, Confusion Matrix, ROC-AUC. |

---

## 🚀 Getting Started (Run the Examples)

To run the example code and notebooks, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [Your Repository URL]
    cd ML_Fundamentals
    ```
2.  **Create and activate the environment:**
    The necessary packages (scikit-learn, numpy, pandas, jupyter) are listed in `environment.yml`.
    ```bash
    # Using Conda
    conda env create -f environment.yml
    conda activate ml-fundamentals-env
    ```
3.  **Run the examples:**
    Navigate to the `examples/` directory and execute any Python script or launch a Jupyter Notebook.
    ```bash
    jupyter notebook examples/KNN_CrossValidation.ipynb
    ```

---

## ✍️ Contribution & Feedback

This repository is primarily a personal learning journal. However, if you spot a factual error or have a suggestion for clarifying a difficult concept, feel free to open an issue!