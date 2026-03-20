# 🏦 Quantum Machine Learning for Credit Card Fraud Detection

This project demonstrates the application of Quantum Machine Learning (QML) in Financial Risk Modelling. Specifically, it compares a **Classical Support Vector Machine (SVM)** with a **Quantum Support Vector Machine (QSVM)** to detect fraudulent credit card transactions.

## 🧠 The Concept
Financial datasets are highly complex and multidimensional. QSVMs map classical data into a high-dimensional quantum Hilbert space using a **Quantum Feature Map**. The theoretical advantage is that data which is not linearly separable in classical space may become linearly separable in quantum space.

## ⚙️ Tech Stack
* **Quantum Computing:** Qiskit, Qiskit Machine Learning
* **Machine Learning:** Scikit-Learn, Pandas
* **Data Visualization:** Matplotlib, Seaborn

## 🔬 Methodology
1. **Data Preprocessing:** Handled massive class imbalance via undersampling.
2. **Dimensionality Reduction:** Used Principal Component Analysis (PCA) to compress features from 30 down to 4. 
3. **Quantum Encoding:** Mapped the 4 classical features to 4 qubits using Qiskit's `ZZFeatureMap` (2 repetitions, linear entanglement).
4. **Model Training:** Calculated a fidelity quantum kernel and passed it into an `sklearn` SVC classifier.

## 📊 Results
<img width="1157" height="490" alt="image" src="https://github.com/user-attachments/assets/c1f39897-3a54-466c-b769-1476c270f23d" />


While current NISQ-era quantum simulators perform similarly to classical models on compressed datasets, this proof-of-concept shows the architecture required to scale financial risk models once fault-tolerant quantum hardware becomes available.

## 🚀 How to Run Locally
1. Clone the repo: `git clone https://github.com/YOUR_USERNAME/Quantum-Finance-Fraud-Detection.git`
2. Install requirements: `pip install qiskit qiskit-machine-learning scikit-learn pandas matplotlib seaborn jupyter`
3. Download the dataset from [Kaggle](https://www.kaggle.com/mlg-ulb/creditcardfraud) and place it in the `/data` folder.
4. Run the Jupyter Notebook!
