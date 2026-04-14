# CatFinder : Binary Image Classification

## 1. Overview

CatFinder is a machine learning project focused on binary image classification (cats vs dogs). It implements a full pipeline from raw image processing to neural network training, with an emphasis on understanding core mechanisms such as feature extraction and learning dynamics.

---
## 2. Results

* The models are able to correctly classify images of cats and dogs
* The pipeline demonstrates successful learning from raw image data
* End to end system: from image preprocessing to prediction

* At best, the model reaches around 60% accuracy using a single hidden layer with 64 neurons. This relatively low performance can be explained by the limited size of the dataset. 

Interestingly, adding more layers does not improve performance. For instance, the following configuration:
neural_network_D(..., hidden_layers=(32, 32), ...), i.e. a two-layer network with 32 neurons per layer,
consistently achieves around 58% accuracy, which is slightly worse than the single-layer model.

This behavior can be explained by the increased difficulty of training deeper networks, especially with limited data. In particular, random initialization and deeper architectures can lead to poor convergence due to issues such as vanishing gradient, making optimization less effective.


---
## 3. Method

### Data preprocessing

* Images are converted into matrix representations
* Pixel values are normalized to ensure stable training
* Basic transformations are applied to standardize inputs

### Feature extraction

* Gradient based features are computed to highlight image structures (edges)
* This step enables better representation of visual information

### Model

* Implementation of:

  * Logistic regression
  * Two layer neural network
  * Multi layer neural network

### Training

* Forward propagation
* Log Loss computation
* Backpropagation implemented from scratch
* Optimization using gradient descent

---

## 4. Data

* Input: images of cats and dogs
* Format: matrix representation of pixel intensities
* Preprocessing includes normalization and optional feature extraction

---

## 5. Project Structure

```
datasets        # images dataset
README.md
utilities.py 
Chats_matriciels.ipynb
```

---

## 6. Notes

This project emphasizes a from-scratch implementation of core machine learning concepts, including neural networks and gradient-based optimization, to build a deeper understanding of underlying mechanisms.

