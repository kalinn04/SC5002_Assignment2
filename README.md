# SC5002
Lab Assignment 2

# SC5002 Lab Assignment 2 – Clustering & Neural Networks

**Course:** SC5002 Artificial Intelligence Fundamentals & Applications (NTU)

## Overview

This lab assignment explores different machine learning techniques, covering unsupervised learning and neural networks through three exercises.

- **Exercise 1 – K-Means Clustering:** Apply K-Means with different values of k to segment retail customers based on Annual Income and Spending Score. Use the Elbow Method to determine the optimal number of clusters and investigate sensitivity to random initialisation.
- **Exercise 2 – Limitations of K-Means:** Apply K-Means to a synthetic dataset containing two interlocking circles. Visualise why K-Means struggles with non-spherical clusters and discuss its limitations.
- **Exercise 3 – Neural Networks:** Select a real-world dataset and develop a neural network to solve a classification or regression problem.

## Files

| File | Description |
|---|---|
| `README.md` | This file |
| `readme_exercise3.md` | Detailed Explanation neural network implementation on selected real-world dataset |
| `bedtime_screentime_sleep_debt.csv` | Dataset |
| `SC5002 Lab Assignment 2_Exercise1 and 2.ipynb` | K-Means clustering, customer segmentation, Elbow Method, and initialisation analysis and K-Means clustering on a synthetic two-circle dataset |
| `SC5002 Lab Assignment 2_Exercise3.ipynb` | Neural network implementation using a selected real-world dataset |

## How to Run

1. Open the respective `.ipynb` notebook in Google Colab or Jupyter Notebook.
2. Upload any required datasets if prompted.
3. Click **Runtime → Run all** in Google Colab.
4. Run the notebook cells sequentially to reproduce the analysis, visualisations, and results.

**Libraries:** numpy, pandas, matplotlib, seaborn, scikit-learn, and PyTorch (where required).

## Exercise 1 – K-Means Customer Segmentation

**Objective:** Segment 20 retail customers based on Annual Income (k$) and Spending Score (1–100).

### Tasks

- Apply K-Means clustering with k=3 and k=5.
- Visualise the resulting clusters using 2D scatterplots.
- Compare the clustering results between different values of k.
- Apply the Elbow Method by calculating WCSS for k=1 to k=6.
- Plot the elbow curve to determine the optimal number of clusters.
- Investigate sensitivity to initialisation by running K-Means with different random seeds.
- Compare cluster assignments and WCSS values to understand how random initialisation affects clustering results.

## Exercise 2 – Limitations of K-Means

**Objective:** Investigate the limitations of K-Means when dealing with non-spherical and complex-shaped clusters.

### Tasks

- Visualise the synthetic 30-point two-interlocking-circles dataset using the true labels:
  - Label 0: Blue
  - Label 1: Red
- Apply K-Means clustering with k=2.
- Visualise the predicted clusters and compare them with the true labels.
- Analyse why K-Means fails to correctly identify the interlocking circular structures.
- Discuss how the spherical cluster assumption makes K-Means unsuitable for complex-shaped data.

## Exercise 3 – Neural Networks

**Objective:** Apply neural networks to solve a real-world machine learning problem using a dataset of choice.

### Tasks

- Select a relevant real-world dataset from Kaggle or other open data sources.
- Identify whether the problem is classification or regression.
- Perform data exploration and preprocessing.
- Develop and train a neural network model.
- Evaluate model performance using appropriate evaluation metrics.
- Analyse the results and discuss potential improvements.

The dataset and model architecture depend on the selected project.

## Conclusion

This assignment provides practical experience with different machine learning techniques, from unsupervised clustering to neural network development.

Exercise 1 explores customer segmentation and the effects of K-Means parameter selection and random initialisation. Exercise 2 demonstrates the limitations of K-Means when applied to non-spherical clusters. Exercise 3 applies neural networks to a real-world dataset to solve a classification or regression problem.

Together, these exercises develop an understanding of machine learning algorithms, their applications, and their limitations.
