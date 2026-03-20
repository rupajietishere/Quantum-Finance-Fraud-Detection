# 🏦 Quantum Machine Learning for Credit Card Fraud Detection

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Qiskit](https://img.shields.io/badge/Qiskit-Latest-blueviolet.svg)
![Scikit-Learn](https://img.shields.io/badge/Scikit_Learn-Latest-orange.svg)
![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)

This project demonstrates the application of Quantum Machine Learning (QML) in Financial Risk Modelling. Specifically, it compares a Classical Support Vector Machine (SVM) with a Quantum Support Vector Machine (QSVM) to detect fraudulent credit card transactions.

## 🧠 The Concept
Financial datasets are highly complex and multidimensional. QSVMs map classical data into a high-dimensional quantum Hilbert space using a Quantum Feature Map. The theoretical advantage is that data which is not linearly separable in classical space may become linearly separable in quantum space.

## ⚙️ Tech Stack
* **Quantum Computing:** Qiskit, Qiskit Machine Learning
* **Machine Learning:** Scikit-Learn, Pandas
* **Data Visualization:** Matplotlib, Seaborn

## 🔬 Methodology
1. **Data Preprocessing:** Handled massive class imbalance via undersampling.
2. **Dimensionality Reduction:** Used Principal Component Analysis (PCA) to compress features from 30 down to 4. 
3. **Quantum Encoding:** Mapped the 4 classical features to 4 qubits using Qiskit's `ZZFeatureMap` (2 repetitions, linear entanglement).
   
<img width="1722" height="625" alt="image" src="https://github.com/user-attachments/assets/f0c593a8-35ae-4c34-9196-41a6ef561cae" />


4. **Model Training:** Calculated a fidelity quantum kernel and passed it into an `sklearn` SVC classifier.

## 📊 Results

<img width="1157" height="490" alt="image" src="https://github.com/user-attachments/assets/54222cca-37de-42ed-b85e-1e3c669f00ec" />


### Performance Breakdown
* **Classical SVM Accuracy:** ~97.5%
* **Quantum SVM Accuracy:** ~65.0%

### Why did the Classical Model outperform the Quantum Model?
At first glance, it appears the classical model is vastly superior. However, this highlights the current realities and constraints of the **NISQ (Noisy Intermediate-Scale Quantum)** era:

1. **Dimensionality Constraints (Information Loss):** To simulate the quantum kernel on a classical CPU in a reasonable timeframe, the dataset had to be heavily compressed using PCA (from 30 features down to 4). This aggressively removes the high-dimensional complexity that a QSVM is theoretically designed to exploit.
2. **Classical Data Advantage:** The underlying dataset is perfectly suited for classical algorithms. The Classical RBF kernel easily draws a hyper-plane between the classes in a compressed 4D space.
3. **Feature Map Optimization:** We utilized a standard `ZZFeatureMap`. The sub-optimal separation in the quantum Hilbert space suggests that a custom, domain-specific quantum feature map is required to capture the specific variances of financial fraud data.

## 🔭 Future Work
To improve the quantum model's performance in future iterations, I plan to:
* Experiment with different Quantum Feature Maps (e.g., PauliFeatureMap or custom hardware-efficient ansatzes).
* Replace the QSVM with a **Variational Quantum Classifier (VQC)** to actively train the parameters of the quantum circuit.
* Run the optimized circuit on real IBM Quantum hardware via the IBM Quantum Cloud.

## 🚀 How to Run Locally
1. Clone the repo: `git clone https://github.com/rupajietishere/Quantum-Finance-Fraud-Detection.git`
2. Install requirements: `pip install qiskit qiskit-machine-learning scikit-learn pandas matplotlib seaborn jupyter pylatexenc`
3. Download the dataset from [Kaggle](https://www.kaggle.com/mlg-ulb/creditcardfraud) and place it in the `/data` folder.
4. Run the Jupyter Notebook!
