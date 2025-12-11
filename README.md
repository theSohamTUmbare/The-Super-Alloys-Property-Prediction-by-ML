# The-Super-Alloys-Property-Prediction-by-ML

This repository contains a Jupyter Notebook that demonstrates an end-to-end machine learning workflow for predicting key properties (melting point and tensile strength) of alloys using composition–property data.


## 🎯 Objectives

To develop and benchmark machine learning models capable of accurately predicting key mechanical properties—specifically melting point and tensile strength—from the chemical composition of high-temperature superalloys, with the ultimate goal of accelerating alloy design cycles, reducing experimental costs, and enabling data-driven discovery of novel compositions for aerospace and defense applications.

## 🔔 Update 
Recently I tried Regression Tree Algorithm on melting point prediction objective and I got **R2 score of 0.984** on these parameters:
``` 
Regression Tree Best Parameters - 
{'criterion': 'squared_error',
 'max_depth': 30,
 'max_features': 1.0,
 'max_leaf_nodes': None,
 'min_samples_leaf': 1,
 'min_samples_split': 2}
```
To explore the hyper parameter tuning and more experiments with regression tree check out the `models\Regression_Trees_on_SuperAlloy_Dataset.ipynb`
[Kaggle_Notebook](https://www.kaggle.com/code/sohamumbare/regression-trees-on-superalloy-dataset)

## 📋 Overview

Materials informatics can accelerate alloy design by replacing costly experiments with rapid ML‑driven screening. In this project, I:

1. **Curated** a pilot dataset of ∼2,800 superalloys (composition + tensile strength + melting point).  
2. **Implemented and tuned**:
   - K‑Nearest Neighbors (KNN)  
   - Support Vector Regression (SVR) with linear, polynomial, and RBF kernels  
   - Feed‑forward Artificial Neural Networks (ANNs), both single‑output and multi‑output  
3. **Compared** performance using MSE and R² metrics.

---

**Kaggle Notebook**:  
[The Super‑Alloys Property Prediction by ML](https://www.kaggle.com/code/sohamumbare/the-super-alloys-property-prediction-by-ml)

**Dataset**:
[Alloy Dataset](https://www.kaggle.com/datasets/sohamumbare/alloy-dataset)

---

## 🗄️ Dataset

- **Source**: Combined multiple public Kaggle datasets on superalloy compositions.  
- **Contents**:  
  - 30 elemental weight‑percent features (e.g., Ni, Fe, Al, Ti, …)  
  - Alloy name  
  - Tensile strength   
  - Melting point 

All data cleaning, normalization, and EDA steps are fully documented in the notebook.

![](/data/alloy_clusters.png)

## 🔧 Methods

1. **Data Preparation**  
   - Handle missing values, normalize weight fractions, visualize distributions.  
2. **Modeling**  
   - **KNN**: Tune `K` via cross‑validation.  
   - **SVR**: Explore linear, polynomial, and RBF kernels.  
   - **ANNs**:  
     - *Single‑Output*: Separate networks for each property.  
     - *Multi‑Output*: A single network predicting both properties jointly.  
3. **Evaluation**  
   - MSE (Mean Squared Error)  
   - R² (Coefficient of Determination)



## 📈 Results

### Melting Point Predictions

|  **Model**        |  **Hyperparameters**  |  **MSE**          |  **R²**           |  
| :---------------: | :--------------------: | :---------------: | :---------------: |
| KNN               | K = 5                  | 21.55             | 0.98              |
| SVR               | Linear Kernel          | 165.24            | 0.91              | 
| SVR               | Polynomial Kernel      | 643.38            | 0.67              | 
| SVR               | RBF Kernel             | 62.90             | 0.97              |
| Single‑Output ANN | 3 linear layers        | 77.04             | 0.96              |
| Multi‑Output ANN  | 3 linear layers        | 117.00            | 0.94              |

### Tensile Strength Predictions

|  **Model**        |  **Hyperparameters**  |  **MSE**          |  **R²**           |  
| :---------------: | :--------------------: | :---------------: | :---------------: |
| KNN               | K = 6                  | 17869.63          | 0.54              |
| SVR               | Linear Kernel          | 31231.43          | 0.19              | 
| SVR               | Polynomial Kernel      | 31676.61          | 0.18              | 
| SVR               | RBF Kernel             | 22915.96          | 0.41              |
| Single‑Output ANN | 3 linear layers        | 19426.28          | 0.50              |
| Multi‑Output ANN  | 3 linear layers        | 20628.87          | 0.47              |

## 🧪 Key Insights

Tensile strength proved more challenging to predict than the melting point. Among the models tested, KNN performed best for predicting both physical properties. However, deeper and more sophisticated ANN models are likely to deliver even better performance than KNN, and I plan to explore them in future work.

--- 

## 🚀 Usage

1. **Open the notebook on Kaggle:  
   https://www.kaggle.com/code/sohamumbare/the-super-alloys-property-prediction-by-ml  
2. **Run all cells** from data loading through model evaluation.  
3. **Experiment** with:
   - Different feature sets  
   - Hyperparameter values  
   - Advanced ML and Deep Learning architectures

Feel free to open issues or discussions on the Kaggle notebook page! 



## 📬 Contact

**Soham Umbare**  
IIIT Raichur  
📧 cs23b1068@iiitr.ac.in

---

⭐ _If you find this work interesting, consider giving it a star on Kaggle & GitHub!_

---
🧑‍💻 Happy Experimenting! 🔬

