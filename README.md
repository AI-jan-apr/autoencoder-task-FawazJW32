# 📌 Autoencoder with MNIST Dataset

## 🚀 Project Overview
This project implements an Autoencoder neural network using the MNIST dataset to perform:

- Image reconstruction  
- Latent feature learning  
- Dimensionality reduction (visualization)  
- Image retrieval using cosine similarity  

The model learns a compressed representation of handwritten digits and uses it for similarity-based search.

---

## 📊 Dataset
- Source: OpenML (mnist_784)  
- Total Samples: 70,000 images  
- Image Size: 28 × 28 (flattened to 784 features)  
- Classes: Digits (0–9)  
- Type: Grayscale  

---

## 🧠 Model Architecture

### Encoder
- Input: 784 features  
- Dense layers: 128 → 64 → 32  
- Output: Latent vector (compressed representation)

### Decoder
- Dense layers: 32 → 64 → 128 → 784  
- Output: Reconstructed image  

---

## ⚙️ Training Setup
- Loss Function: Mean Squared Error (MSE)  
- Optimizer: Adam  
- Epochs: 20  
- Batch Size: 256  

### Training Objective
The model is trained to reconstruct the input:
Input = Output (unsupervised learning)

---

## 📉 Results

### Reconstruction
- The model successfully reconstructs handwritten digits  
- Outputs are slightly blurred (expected due to compression)  

### Latent Space Learning
- The encoder captures meaningful features  
- Similar digits produce similar latent vectors  

---

## 📊 Dimensionality Reduction
- Latent vectors (32D) are reduced to 2D using PCA  
- Visualization shows clustering of similar digits  

Insight:
Digits with similar shapes (e.g., 3 and 5) appear closer in latent space  

---

## 🔎 Image Retrieval System

### Method
1. Encode query image into latent space  
2. Encode training dataset  
3. Compute cosine similarity  
4. Retrieve top-5 most similar images  

### Key Idea
Similarity is based on learned features, not raw pixels  

---

## 🛠️ Technologies Used
- Python  
- TensorFlow / Keras  
- Scikit-learn  
- NumPy  
- Matplotlib  

---

## 📁 Project Structure
```text
autoencoder-mnist/
│
├── autoencoder_task.ipynb
├── README.md
```
---

## ▶️ How to Run
1. Open the notebook:
```text
autoencoder_task.ipynb
```
### Cosine Similarity
- Measures similarity between vectors  
- Used for retrieval  