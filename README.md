# SC5002_Assignment2
Lab Assignment 2

# SC5002 Lab Assignment – Sleep Debt Classification Using Neural Networks

**Course:** SC5002 Artificial Intelligence Fundamentals & Applications (NTU)

## Overview

SC5002 Lab Assignment 2 focuses on developing a Feedforward Neural Network (FNN) to classify sleep debt categories based on demographic information, bedtime smartphone usage, lifestyle habits, and sleep-related characteristics.

This is a multiclass classification problem with four target categories:
- **Mild Deficit**
- **Moderate Debt**
- **Optimal Recovery**
- **Severe Sleep Debt**

The project investigates whether machine learning can identify patterns between bedtime smartphone usage and sleep outcomes.

## Files

| File | Description |
|---|---|
| `SC5002_Assignment2.ipynb` | Completed Google Colab notebook containing data preprocessing, EDA, neural network implementation, training, and evaluation |
| `bedtime_screentime_sleep_debt.csv` | Dataset used for sleep debt classification |
| `README.md` | This file |

## How to Run

1. Open `SC5002_Assignment2.ipynb` in Google Colab (File → Upload notebook).
2. Upload `bedtime_screentime_sleep_debt.csv` when prompted, or place it in the expected working directory.
3. Click **Runtime → Run all**.
4. The notebook performs data preprocessing, exploratory analysis, model training, hyperparameter experiments, and evaluation.

**Libraries:** PyTorch, numpy, pandas, matplotlib, seaborn, scikit-learn.

## Dataset

**Dataset:** Bedtime Screen Time and Sleep Debt Dataset (Kaggle).

- **Total observations:** 8,500
- **Original columns:** 18
- **Target:** `sleep_debt_category`
- **Input features after preprocessing:** 28
- **Missing values:** 0
- **Duplicate rows:** 0

The input features cover four main areas:
- **Demographics:** Age, gender, occupation type, chronotype.
- **Smartphone Usage:** Bedtime phone minutes, primary bedtime app, screen brightness, blue-light filter.
- **Lifestyle:** Evening caffeine consumption, physical activity.
- **Sleep Characteristics:** Sleep latency, total sleep hours, deep sleep percentage, REM sleep percentage, morning alarm snoozes.

The `user_id` and `next_day_fatigue_score` columns were removed during preprocessing.

## Data Preprocessing

- Target categories were encoded using `LabelEncoder`.
- Numerical features were imputed using the median and standardised.
- Categorical features were imputed using the most frequent value and one-hot encoded.
- Preprocessing was fitted only on the training dataset to prevent data leakage.
- Stratified splitting was used to maintain class proportions.

| Dataset | Percentage | Observations |
|---|---:|---:|
| Training | 60% | 5,100 |
| Validation | 20% | 1,700 |
| Testing | 20% | 1,700 |

## Model Architecture

A Feedforward Neural Network with two hidden layers was implemented using PyTorch.

| Layer | Neurons | Activation |
|---|---:|---|
| Input | 28 | None |
| Hidden Layer 1 | 64 | ReLU |
| Hidden Layer 2 | 32 | ReLU |
| Output | 4 | Raw logits |

**Training Configuration:**

| Parameter | Value |
|---|---|
| Optimiser | Adam |
| Loss Function | CrossEntropyLoss |
| Learning Rate | 0.001 |
| Batch Size | 32 |
| Maximum Epochs | 100 |
| Random Seed | 42 |

## Results

### Baseline Model Performance

| Dataset | Accuracy |
|---|---:|
| Training | 99.16% |
| Validation | 95.53% |
| Testing | 94.59% |

### Classification Report

| Category | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Mild Deficit | 0.96 | 0.95 | 0.95 |
| Moderate Debt | 0.97 | 0.95 | 0.96 |
| Optimal Recovery | 0.94 | 0.99 | 0.96 |
| Severe Sleep Debt | 0.75 | 0.84 | 0.79 |

## Hyperparameter Experiments

### Learning Rate Comparison

| Learning Rate | Training Accuracy | Validation Accuracy | Test Accuracy | Test Loss |
|---|---:|---:|---:|---:|
| 0.1 | 96.16% | 96.12% | 96.12% | 0.1079 |
| 0.01 | 97.20% | 95.59% | 95.12% | 0.1049 |
| 0.001 | 98.63% | 97.00% | 95.94% | 0.0870 |

A learning rate of 0.001 achieved the lowest test loss and highest validation accuracy.

### Hidden Layer Comparison

| Model | Hidden Layers | Test Accuracy |
|---|---|---:|
| Model A | 32 | 96.47% |
| Model B | 64, 32 | 96.00% |
| Model C | 128, 64, 32 | 95.76% |

## Key Findings

- The baseline model achieved **94.59% test accuracy**, demonstrating good overall classification performance.
- The model performed well in predicting Mild Deficit, Moderate Debt, and Optimal Recovery, but had more difficulty identifying Severe Sleep Debt (F1-score: 0.79).
- The baseline model showed signs of overfitting, with training accuracy (99.16%) higher than test accuracy (94.59%).
- Validation loss began increasing after approximately epoch 20, suggesting that the model started overfitting during later training epochs.
- A learning rate of 0.001 achieved the lowest test loss (0.0870) and highest validation accuracy (97.00%).
- The simplest architecture (Model A: 32 hidden neurons) achieved the highest recorded test accuracy (96.47%), suggesting that a more complex network does not necessarily perform better.
- Misclassifications may be caused by class imbalance, overlapping feature distributions, and missing relevant information.

## Limitations & Future Improvements

- The target categories are imbalanced, particularly Severe Sleep Debt.
- The dataset may not fully represent real-world sleep behaviours.
- The model does not account for factors such as stress levels, sleep environment, and individual health differences.
- Overfitting may affect the model's ability to generalise to unseen data.

Possible improvements:
- Reduce the number of input features.
- Use class-weighted loss to address class imbalance.
- Compare performance with Logistic Regression, Random Forest, and XGBoost.
- Apply SHAP for feature importance analysis.
- Experiment with different learning rates, batch sizes, and network architectures.
- Evaluate the model on an independent dataset.

## Conclusion

The project demonstrates the potential of feedforward neural networks for classifying sleep debt categories using demographic, smartphone usage, lifestyle, and sleep-related features.

The baseline model achieved 94.59% test accuracy. However, overfitting, class imbalance, and misclassification remain important challenges. Further improvements in regularisation, dataset quality, and model validation could improve generalisation.

**Disclaimer:** This project was developed for academic purposes. Predictions should not be interpreted as medical diagnoses or professional sleep assessments.
