# 🖐️ Handwritten Character Recognition (MNIST & EMNIST)

A deep learning project implementing **Convolutional Neural Networks (CNN)** to recognize handwritten digits and letters with high accuracy.

## 📊 Performance Results

| Dataset | Classes | Preprocessing Strategy | Final Accuracy |
| :--- | :---: | :--- | :---: |
| **MNIST** (Digits) | 10 (0-9) | Normalization only | **99.03%** |
| **EMNIST** (Letters) | 26 (A-Z) | **Rotation (270°) + Flip** + Norm | **93.81%** |

> 💡 **Key Insight:** The EMNIST dataset images are stored rotated 90° clockwise. Applying `tf.image.rot90(k=3)` and horizontal flipping was critical to achieving >93% accuracy. Without this, the model fails to recognize upright characters.

## 🛠️ Tech Stack
- **Framework:** TensorFlow 2.x / Keras
- **Architecture:** Custom CNN with BatchNormalization & Dropout
- **Data:** MNIST & EMNIST (via TensorFlow Datasets)

## 🧠 Model Architecture Highlights

### 1. MNIST Model (Digits)
- **Depth:** 3 Convolutional Layers (32 → 64 → 128 filters)
- **Regularization:** BatchNormalization after every conv layer, Dropout (0.5) in dense layers.
- **Result:** Converged rapidly to 99% accuracy within 10 epochs.

### 2. EMNIST Model (Letters)
- **Depth:** 2 Convolutional Layers (32 → 64 filters) optimized for finer character details.
- **Regularization:** Aggressive Dropout (0.25/0.5) to prevent overfitting on similar letters (e.g., 'O' vs 'Q').
- **Result:** Achieved peak validation accuracy of **93.81% at Epoch 8**.


## 📁 Project Structure
- `MNIST_task3.ipynb`: Complete code for digit recognition.
- `EMNIST_task3.ipynb`: Complete code for letter recognition (includes rotation logic).
- `models/`: Saved `.h5` weights for deployment.
- `outputs/`: Generated evaluation plots.

## 🚀 How to Run
1. Clone this repository.
2. Open the `.ipynb` files in Google Colab or Jupyter Notebook.
3. Run all cells to retrain models or load saved weights from the `models/` folder.

## 📄 License
MIT License
