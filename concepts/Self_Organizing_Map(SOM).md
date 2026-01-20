# Self Organizing Map - SOM

SOM is a type of unsupervised neural network developed by **Teuvo Kohonen**. It is used mainly for visualizing high-dimensional data by projecting it onto a low-dimensional (usually 2D) grid.

Think of SOM as a clustering + dimensionality reduction tool that maintains the topological structure (i.e., similar things stay close together).

---

## Key Concepts

1. **Unsupervised Learning**
SOM doesn’t need labeled data. It learns patterns by identifying similarities in input data and grouping them together.

2. **Structure**
* It consists of:
    * **Input layer**: Each node receives the input vector.
    * **Output layer (map)**: A 2D grid of neurons (like a sheet), where each neuron has a weight vector of the same dimension as the input data.
    
3. **Training Process** : step by step

    1. Initialize weights randomly for each neuron in the map.
    2. For each input data point:
        * **Find the Best Matching Unit (BMU)** – the neuron whose weights are closest to the input.
        * Update the weights of the BMU and its neighboring neurons to become more like the input.
    3. Repeat the process for multiple iterations, slowly reducing the learning rate and neighborhood size.

    **Result**: Similar data points get mapped near each other on the grid.

---

## Real-Life Analogy

Imagine arranging books in a library with no labels, but based on their content similarity. Books about data science will naturally cluster together, while novels will be in a different area—but close novels will sit near each other. That’s what SOM does with your data!

---

## Example Use Cases

* Customer segmentation in marketing
* Image compression (by mapping similar pixel patterns)
* Pattern recognition
* Anomaly detection
* Document classification

---

## Mathematically speaking

* Let input vector: X = [x₁, x₂, ..., xₙ]
* Each neuron has a weight vector W = [w₁, w₂, ..., wₙ]
* Distance = Euclidean:
    
    Distance=Σ(xi−wi)2\text{Distance} = \sqrt{\sum (x_i - w_i)^2}Distance=Σ(xi−wi)2

* BMU = neuron with **minimum distance** to X
* Update rule:
    
    W(t+1)=W(t)+α(t)⋅h(t)⋅(X−W(t))W(t+1) = W(t) + \alpha(t) \cdot h(t) \cdot (X - W(t))W(t+1)=W(t)+α(t)⋅h(t)⋅(X−W(t))
    Where:
    *  α(t) = learning rate
    * h(t) = neighborhood function

---

## Advantages
* Great for visualizing high-dimensional data
* Preserves topology
* Helps in clustering and dimensionality reduction

## Limitations
* Requires tuning (grid size, learning rate, iterations)
* Doesn’t scale well to very large datasets