# Framework for Evasion and Validation of Industrial Control Systems (FEVA-ICS)

This project provides a Jupyter Notebook-based **benchmarking framework** for evaluating the **adversarial robustness** of **Machine Learning-based Intrusion Detection Systems (IDS)** and **Anomaly Detectors** in **Industrial Control Systems (ICS)**.

The framework is implemented entirely in a single notebook: `framework.ipynb`.

## 📌 Overview

- ⚔️ Evaluate ML-based ICS-IDS under various adversarial attacks
- 🧠 Supports IDS models of different architectures (gradient and non-gradient based)
- 🧪 Measures robustness using key metrics like Accuracy, Recall, and Precision
- 🛠️ Designed for reproducibility and ease of extension

## 📁 Files

- `framework.ipynb` – Main notebook containing the full pipeline:
- Data loading
- Trained Model loading
- Model Stealing
- Evasion Attacks
- Evaluation

## ⚙️ Customization: Parameters, Dataset, and Targeted Model

The framework is **fully customizable**:

- 🔧 **Change the dataset**: Use your own or public datasets like SWaT or BATADAL.
- 🎯 **Upload your targeted NIDS**: Upload your own executable targeted ML-based NIDS and Anomaly Detector (in pickle, joblib or h5 format).
- 🧪 **Adjust attack or training parameters** to test different robustness scenarios.

### 🔍 Parameter List

| Parameter           | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `NUM_FEATURES`       | Number of features present in the dataset                                    |
| `EPOCHS`             | Number of training epochs for the surrogate model                                    |
| `TIMESTEPS`         | Timesteps to consider at once while spliting the dataset for training and test                                   |
| `N`        | Batch size for CorrShift Attack                                |
| `epsilon_normal`            | Attack perturbation magnitude for whitebox attacks on normal datapoints                                     |
| `epsilon_attack`            | Attack perturbation magnitude for whitebox attacks on attack datapoints                                     |
| `k_normal`            | Number of components to be perturbed on normal datapoints for FGSM-L0 attack                                   |
| `k_attack`            | Number of components to be perturbed on attack datapoints for FGSM-L0 attack                                   |
| `alpha_normal_pgd`            |  Step size of PGD attack for normal samples                                  |
| `alpha_attack_pgd`            |  Step size of PGD attack for attack samples                                  |
| `alpha_bb_normal`            |  Perturbation coefficient of CorrShift Attack for normal samples                                |
| `alpha_bb_attack`            |  Perturbation coefficient of CorrShift Attack attack samples                                  |
| `iterations`             | Iterations in PGD attack   |
| `access`             | Access to the NIDS (blackbox/whitebox)   |
| `confidence`             | Confidence factor of Carlini and Wagner loss  |
| `protected_cols`  | Features that should not be modified in adversarial examples                |
|---------------------|-----------------------------------------------------------------------------|

> ℹ️ Modify these values directly in the notebook cells as per your experimental setup.



## ✅ Requirements

Make sure you have the following installed:

- Python 3.8+
- Jupyter Notebook or JupyterLab
- Recommended libraries:
  - `numpy`
  - `pandas`
  - `scikit-learn`
  - `matplotlib`
  - `seaborn`
  - `tensorflow`


You can install them using:

```bash
pip install -r requirements.txt




