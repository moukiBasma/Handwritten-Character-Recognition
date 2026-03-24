# Handwritten Recognition (MNIST, EMNIST & OCR)

A deep learning project recognizing handwritten digits, letters, and full words using custom Convolutional Neural Networks (CNNs) and a pre-trained CRNN engine.

## Results Overview

| Task | Dataset/Method | Accuracy/Confidence |
| :--- | :--- | :--- |
| **Digits (0-9)** | MNIST (Custom CNN) | **99.03%** |
| **Letters (A-Z)** | EMNIST (Custom CNN) | **93.81%** |
| **Words** | EasyOCR (Pre-trained CRNN) | **~92% Average** |

**Key Achievement:** Identified and fixed a critical preprocessing issue in the EMNIST dataset where images were rotated 90 degrees. By implementing `rot90` and horizontal flipping, letter recognition accuracy improved from below 60% to **93.81%**.

## Tech Stack
*   **Core Framework:** TensorFlow 2.x, Keras
*   **OCR Engine:** EasyOCR (CRNN + CTC architecture)
*   **Tools:** OpenCV, Matplotlib, Google Colab (T4 GPU)

## Quick Start
1.  Open the provided notebooks in Google Colab.
2.  Run the setup cell to mount Google Drive for automatic result saving.
3.  Execute all cells to train the digit/letter models or run word recognition on custom images.

## Project Structure
```text
CodeAlpha_HandwrittenRecognition/
├── notebooks/          # Code for MNIST, EMNIST, and OCR tasks
├── models/             # Saved .h5 weights for Digits and Letters
├── images/             # Test images (test1.png through test9.png)
└── results/            # JSON reports, summaries, and visualization plots
```

## Future Work
*   Train a custom CRNN model from scratch using the IAM Handwriting Database.
*   Deploy the solution as a real-time web application using Streamlit.
*   Expand language support beyond English to include Arabic, French, and others.

