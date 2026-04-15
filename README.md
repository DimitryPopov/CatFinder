# CatFinder : Neural Networks from Scratch for Image Classification

## 1. Overview

CatFinder is a from-scratch implementation of neural networks applied to binary image classification (cats vs dogs).

The goal is not performance, but understanding:

* how neural networks learn
* how training behaves in practice
* and why increasing model complexity does not always improve results

---
## 2. Results

* Best performance: **~60% accuracy** with a single hidden layer (64 neurons)
* Deeper networks perform worse (**~58% with 2 layers**)

Key observation:

> Increasing model depth without sufficient data can degrade performance rather than improve it.

This behavior highlights:

* sensitivity to initialization
* difficulty of optimization
* limitations of small datasets

Interestingly, adding more layers does not improve performance. For instance, the following configuration:
neural_network_D(..., hidden_layers=(32, 2), ...), i.e. a two-layer network with 32 neurons per layer,
consistently achieves around 58% accuracy, which is slightly worse than the single-layer model.

This behavior can be explained by the increased difficulty of training deeper networks, especially with limited data. In particular, random initialization and deeper architectures can lead to poor convergence due to issues such as \bold{vanishing \ gradient}, making optimization less effective.


---
## 3. Method

### Data preprocessing

* Images converted into matrices
* Normalization of pixel values

### Feature extraction

* Gradient based features are computed to highlight image structures (edges)
* This step enables better representation of visual information

### Model

* Logistic regression
* Two-layer neural network
* Multi-layer neural network

### Training

* Forward propagation
* Log Loss 
* Backpropagation implemented from scratch
* Optimization using gradient descent

---

## 4. Data

* Input: images of cats and dogs
* Format: pixel intensity matrices
* Dataset size is limited so it impacts performance

---

## 5. Project Structure

```
datasets/
README.md
utilities.py
Chats_matriciels.ipynb
```

---

## 6. Notes

This project focuses on understanding the behavior of neural networks rather than maximizing accuracy.

It shows that:

* simple models can outperform deeper ones on small datasets
* increasing complexity without sufficient data leads to unstable training

For detailed visualizations and intermediate results, see the Jupyter notebook.


