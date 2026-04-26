# EEG-Based Mental State Classification

This project is an end-to-end Machine Learning pipeline that predicts human mental states (Concentrating, Relaxed and Neutral) using brainwave signals collected from Muse (EEG device providing real-time neurofeedback).


## Architecture & Data Pipeline

To handle the high-dimensional and noisy nature of biological signals, the following data engineering steps were implemented:
1. **Data Preprocessing:** Applied `StandardScaler` to normalize the data (mean = 0, variance = 1).
2. **Dimensionality Reduction (PCA):** To prevent a Dimensionality Curse on the 988-feature dataset, Principal Component Analysis (PCA) was utilized. The feature space was reduced to **454 principal components**, successfully retaining 95% of the original variance.
3. **Classification Model:** Trained a Random Forest Classifier (100 estimators), which is highly effective for complex tabular data and non-linear boundaries.


## Model Performance

The model achieved an overall **Accuracy of 90.93%** on the unseen test dataset. The class-wise performance (F1-Score) is as follows:
* **Relaxed (Class 2):** 95%
* **Neutral (Class 0):** 91%
* **Concentrating (Class 1):** 87%


## 💻 Installation & Usage

To run this project locally:

1. Clone the repository and activate a virtual environment:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/eeg-mental-state.git](https://github.com/ArdaSAAT/EEG-Based-Mental-State-Classification.git)
   cd eeg-mental-state
   python -m venv venv
   source venv/bin/activate # For Windows: venv\Scripts\activate
