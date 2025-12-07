# 🧠 Comparative Analysis of Sampling Techniques for Imbalanced Classification

A Multi-Dataset Empirical Study

This repository contains experimental code, datasets, and results from a research study evaluating the effectiveness and computational trade-offs of various resampling strategies for imbalanced classification problems. The work compares five commonly used sampling techniques across multiple imbalance severities and two classifier families.

📄 The research is documented in the paper:
“Evaluating Resampling Strategies for Imbalanced Classification: A Comparative Study Across Varying Imbalance Ratios” by Marwan Eslam Ouda 

Research_paper(Imbalancing data…

## ✨ Project Overview

Class imbalance occurs when one class significantly outnumbers another, leading traditional classifiers to favor the majority class. This project investigates:

Which resampling method works best for a given imbalance severity?

Do complex synthetic oversampling techniques actually outperform simpler ones?

How does computational cost influence method selection?

## 🧪 Methods Compared
Strategy	Category	Description
Baseline	—	No change to original data distribution
Random Oversampling	Oversampling	Duplicates minority class samples
Random Undersampling	Undersampling	Removes majority class samples
SMOTE	Synthetic Oversampling	Interpolates new minority samples
ADASYN	Adaptive Synthetic	Generates samples in sparse minority areas

Two classifiers were used:

Random Forest (RF)

XGBoost (XGB)

## 📊 Datasets Used
Dataset	Domain	Imbalance Ratio	Role
Pima Indians Diabetes	Medical	1.87:1	Moderate imbalance
Credit Card Fraud	Finance	601:1	Extreme imbalance
Heart Disease	Medical	1.05:1	Near-balanced baseline
## 🚀 Key Findings

🔹 From experimental results in the paper 

Research_paper(Imbalancing data…

:

XGBoost baseline (no resampling) achieved best performance on extremely imbalanced data (F1 = 0.845)

Random undersampling:

Best for moderate imbalance (F1 = 0.681)

Catastrophic failure on extreme imbalance (F1 dropped to 0.086)

SMOTE / ADASYN:

Provide small gains at high computational cost

Underperformed on extremely rare classes

📌 No one-size-fits-all method → Performance depends heavily on imbalance severity.


## ⚙️ Installation & Setup
# Clone the repo
git clone https://github.com/<username>/<repo-name>.git
cd <repo-name>

# Install dependencies
pip install -r requirements.txt


Main Python libraries:

scikit-learn

imbalanced-learn

xgboost

pandas, numpy, matplotlib, seaborn

## ▶️ How to Run Experiments

Run the Jupyter Notebook:

jupyter notebook notebooks/Comparative_Analysis_of_Sampling_Techniques.ipynb


Or execute scripts inside src/ to train and evaluate using a specific dataset.

## 📈 Evaluation Metrics

All techniques were compared using:

F1-Score

Precision

Recall

ROC-AUC

Training Time (Efficiency)

✔️ Recommendations for Practitioners
Scenario	Best Strategy
Imbalance < 5:1	No resampling needed
5:1 – 20:1	Random over/undersampling
> 20:1	Baseline boosting (XGBoost)
Minority < 500 samples	❌ Avoid undersampling
Limited compute budget	Random oversampling
🔮 Future Work

Hybrid resampling + cost-sensitive learning

Multi-class imbalanced problems

Application to deep learning classifiers

Theoretical modeling of SMOTE failure cases

## 🙌 Acknowledgments

Thanks to the open-source communities behind
Scikit-Learn, Imbalanced-Learn, and XGBoost for providing the tools used in this work.

## 📬 Contact

Developed by: Marwan Eslam Ouda
Faculty of Computer and AI – Benha University
📧: marawan403465@fci.bu.edu.eg
