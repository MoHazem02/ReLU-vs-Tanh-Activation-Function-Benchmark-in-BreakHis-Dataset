# 🧬 Activation Functions in CNNs — A Comparative Study (ReLU vs Tanh)

This project compares the performance of **ReLU** and **Tanh** activation functions in a **Convolutional Neural Network (CNN)** designed to classify **breast histopathology images** from the **BreakHis dataset** into *benign* or *malignant* categories.

---


<img width="1160" height="504" alt="Untitled" src="https://github.com/user-attachments/assets/93597051-db5b-4e03-a0db-452eeee17f92" />


## 📁 Project Overview

This study aims to explore how the choice of activation function affects a CNN’s **training behavior**, **accuracy**, and **convergence** in a real-world medical imaging dataset.

Two models were built using identical architectures — differing only in their hidden-layer activations:
- Model 1 → `ReLU`
- Model 2 → `Tanh`

Both models used:
- **Sigmoid** activation in the output layer (binary classification)
- **Binary cross-entropy** loss
- **Adam optimizer**

---

## 🧩 Model Architecture

| Layer Type | Filters / Units | Activation | Notes |
|-------------|----------------|-------------|--------|
| Conv2D | 32 | ReLU / Tanh | 3×3 kernel, same padding |
| MaxPooling2D | — | — | 2×2 pool size |
| Conv2D | 64 | ReLU / Tanh | 3×3 kernel |
| MaxPooling2D | — | — | 2×2 pool size |
| Conv2D | 128 | ReLU / Tanh | 3×3 kernel |
| MaxPooling2D | — | — | 2×2 pool size |
| Flatten | — | — | — |
| Dense | 128 | ReLU / Tanh | Fully connected |
| Dense | 64 | ReLU / Tanh | Fully connected |
| Dense | 1 | Sigmoid | Output layer |

---

## ⚙️ Training Details

| Parameter | Value |
|------------|--------|
| Image Size | 96×96×3 |
| Epochs | 10 |
| Batch Size | 32 |
| Optimizer | Adam (lr = 0.001) |
| Loss Function | Binary Crossentropy |
| Validation Split | 20% |

---

## 📊 Results

| Metric | ReLU | Tanh |
|---------|------|------|
| **Validation Accuracy** | ~86% | ~69% |
| **Test Accuracy** | **0.867** | **0.686** |
| **Observation** | ReLU achieved faster convergence and higher accuracy compared to Tanh, which struggled due to vanishing gradients. |

---

## 🧩 Key Insights

- **ReLU outperforms Tanh** in deeper CNNs due to reduced vanishing gradient effects.  
- Tanh can still be effective for shallow networks or small datasets but saturates faster.  
- Proper normalization and balanced datasets are crucial for fair activation comparisons.

---

## 🚀 Technologies Used

- **Python 3**
- **TensorFlow / Keras**
- **OpenCV**
- **NumPy**
- **Matplotlib**
- **tqdm**

---

<img width="790" height="590" alt="Untitled" src="https://github.com/user-attachments/assets/f63f4f76-0a3d-4c16-b9ab-edf3b8ef0b8e" />


## 🧠 Future Work

- Extend to additional activation functions (LeakyReLU, ELU, Swish)
- Apply model interpretability (Grad-CAM)
- Evaluate transfer learning on BreakHis (using VGG16 / ResNet)

---

## 👨‍💻 Author

**Mohamed Hazem**  
Biomedical and Data Engineering Student  
🔗 [LinkedIn](https://www.linkedin.com/in/mohamed-hazem01/) &nbsp;&nbsp; 💻 [GitHub](https://github.com/MoHazem02)

---

## 🏁 Conclusion

This project demonstrates how a **single design choice — activation function —** can significantly influence CNN learning dynamics, stability, and performance, especially in **medical image classification** tasks.

---

⭐ **If you found this project helpful, consider giving it a star!**
