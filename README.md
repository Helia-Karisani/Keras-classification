# Keras MNIST Classification

## Description
This project builds a neural network using Keras to classify handwritten digits from the MNIST dataset. It demonstrates the full pipeline: data loading, preprocessing, model training, evaluation, and model persistence.

---

## Dataset

The MNIST database, which stands for Modified National Institute of Standards and Technology, is a well-known collection of handwritten digit images frequently used in image processing and machine learning for both training and evaluation.

It includes 60,000 training images and 10,000 test images, with the digits written by high school students and employees of the U.S. Census Bureau.

Keras has MNIST dataset as part of its API.

Loading MNIST dataset. It is readily divided into sets of training and test sets.

According to the dataset's documentation, we should have 60000 images in X_train and 10000 images in the X_test.

---

## Data Preprocessing

 we need to flatten the images into one-dimensional vectors, each of size 1 x (28 x 28) = 1 x 784.

divide target variables to categories for classification problems.
converting the class labels into binary class vectors.

### What is happening here (plain explanation)
- Each 28×28 image is converted into a vector of length 784
- Labels (0–9) are converted into one-hot vectors

Example:
- Label `3` → `[0,0,0,1,0,0,0,0,0,0]`

---

## Model

Build a neural network

### Architecture (general)
- Input layer: 784 features
- Hidden layers: Dense (fully connected)
- Output layer: 10 neurons (digits 0–9)
- Activation: typically ReLU (hidden), Softmax (output)

---

## Math Behind the Model (Plain Text)

### Forward Pass
Each layer computes:

z = W*x + b  
a = activation(z)

Where:
- W = weights
- x = input
- b = bias
- a = output of layer

---

### Softmax (Output Layer)
Transforms outputs into probabilities:

softmax(z_i) = exp(z_i) / sum(exp(z_j))

This ensures:
- All outputs are between 0 and 1
- Sum of outputs = 1

---

### Loss Function (Categorical Cross-Entropy)

Loss = - sum(y_i * log(p_i))

Where:
- y_i = true label (one-hot)
- p_i = predicted probability

---

### Training (Gradient Descent)

Weights are updated using:

W = W - learning_rate * gradient

Meaning:
- The model adjusts weights to reduce error step-by-step

---

## Evaluation

printing the accuracy and corresponding error

### Metrics
- Accuracy = correctly predicted / total samples
- Error = 1 - accuracy

---

## Model Saving and Loading

Sometimes we might not be able to train the model again everytime we want to use it. But Keras let us to save our model so that we can use it later.

When we are ready to use our model again, we can use the load_model function from keras.saving.

---

## Workflow Summary

1. Load MNIST dataset  
2. Flatten images (28x28 → 784)  
3. Normalize inputs (if applied)  
4. Convert labels to one-hot encoding  
5. Build neural network  
6. Train model  
7. Evaluate performance  
8. Save model  
9. Reload model for reuse  

---

## Requirements

- Python 3.x
- TensorFlow / Keras
- NumPy

---

## How to Run

1. Install dependencies:
   ```
   pip install tensorflow numpy
   ```

2. Run the notebook:
   - Open in Jupyter Notebook or VSCode
   - Execute cells sequentially

---

## Notes

- Each block in the notebook is modular — run them step by step
- Make sure preprocessing is done before training
- Model saving allows reuse without retraining

---

## Conclusion

This project demonstrates a standard deep learning classification pipeline using Keras. It highlights how neural networks can effectively learn patterns from image data and classify them with high accuracy.
