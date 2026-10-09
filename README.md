# SC5002 — Artificial Intelligence Fundamentals & Applications

**Lab Assignment 1 | 2026 Semester 1**  
**Nanyang Technological University (NTU)**

## Overview

This repository contains the Google Colab notebook for Part 2 of the SC5002 Lab Assignment. The project uses the California Housing dataset to compare **Linear Regression** and **Ridge Regression**, focusing on how the Ridge regularisation parameter (`alpha`) affects predictive performance.

The notebook covers dataset preparation, feature scaling, model evaluation using **5-fold cross-validation**, and visual comparison of model scores.

> **Repository scope:** This repository contains the practical machine-learning notebook for Part 2. The written search-algorithm work, AI prompting logs, and presentation are submitted separately as part of the assignment.

## Repository Contents

- **Google Colab notebook (`.ipynb`)** — Python code, model evaluation outputs, and performance-comparison bar chart.
- **`README.md`** — Project overview, methodology, results, and instructions for running the notebook.

## Dataset

The notebook loads the **California Housing dataset** using `sklearn.datasets.fetch_california_housing` and selects a reproducible sample of **1,000 observations** (`random_state=42`).

- **Target variable:** `MedHouseVal` (median house value).
- **Input features:** `MedInc`, `HouseAge`, `AveRooms`, `AveBedrms`, `Population`, `AveOccup`, `Latitude`, and `Longitude`.

## Methodology

1. Load the California Housing dataset and display the first five rows.
2. Separate the input features (`X`) from the target (`y`).
3. Apply `StandardScaler` to the numerical features.
4. Split the sample into training (80%) and test (20%) subsets using `random_state=42`.
5. Evaluate Linear Regression and Ridge Regression (`alpha = 0.1`, `10.0`, and `1000.0`) using **5-fold cross-validation** on the training data, with **R²** as the metric.
6. Generate a bar chart comparing the mean cross-validation R² scores.

## Results

The following results were obtained in the assignment notebook:

| Model | Alpha | Mean 5-Fold CV R² |
| --- | ---: | ---: |
| Linear Regression | — | 0.6457 |
| Ridge Regression | 0.1 | 0.6457 |
| Ridge Regression | 10.0 | 0.6443 |
| Ridge Regression | 1000.0 | 0.3574 |

### Key Findings

- **Linear Regression and Ridge (`alpha = 0.1`)** achieved the highest reported scores, tied to four decimal places.
- **Ridge (`alpha = 10.0`)** performed only slightly worse than Linear Regression, suggesting that moderate regularisation made little difference in this experiment.
- **Ridge (`alpha = 1000.0`)** performed substantially worse. Such a strong penalty can shrink coefficients excessively and cause **underfitting**, reducing the model's ability to capture useful relationships.

These findings illustrate the importance of selecting an appropriate regularisation strength rather than assuming that a larger penalty always improves generalisation.

## How to Run

1. Open [Google Colab](https://colab.research.google.com/).
2. Select **File → Open notebook → GitHub**, then find or paste the URL of this repository and select its `.ipynb` file. Alternatively, download the notebook from GitHub and upload it to Colab.
3. Select **Runtime → Run all**.
4. Review the displayed dataset rows, mean cross-validation R² scores, and comparison chart.

The notebook uses **Python 3** with the following libraries:

- NumPy
- Pandas
- Matplotlib
- Scikit-learn

These libraries are commonly available in Google Colab. The California Housing dataset is fetched when the notebook runs, so an internet connection may be required.

## AI-Assisted Learning

Generative AI was used as a learning aid to clarify the target and input features, the purpose of feature scaling, differences between Linear and Ridge Regression, the value of cross-validation, and the relationship between regularisation and underfitting. The related prompts and reflections are documented in the separately submitted assignment report.


## Author

- **Name:** Suu Wai Naing
- **Matric Number:** U2521170B

---

*SC5002 — Artificial Intelligence Fundamentals & Applications | Lab Assignment 1 2026 S1*
