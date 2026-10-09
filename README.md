# SC5002 Artificial Intelligence Fundamentals & Applications

## Lab Assignment — 2026 Semester 1

This repository contains the Google Colab notebook for the **SC5002 Artificial Intelligence Fundamentals & Applications** lab assignment at Nanyang Technological University (NTU). The assignment covers **classical search algorithms** and **applied machine learning**, with generative AI used as a learning assistant to explain concepts and review working.

## Assignment Overview

### Part 1: Classical Search & Problem Solving

The theoretical component investigates:

- **Breadth-First Search (BFS)** for exploring a directed graph level by level.
- **A\* Search** using the evaluation function \(f(n) = g(n) + h(n)\), where \(g(n)\) is the path cost and \(h(n)\) is the heuristic estimate.
- **8-puzzle solving** using A\* with node depth as \(g(n)\) and the number of misplaced numbered tiles as \(h(n)\).

The submitted report presents the graph traversal calculations, the A\* evaluation table, the 8-puzzle search working, and reflections on AI-assisted checking.

**Reported graph-search findings:**

| Algorithm | Reported path | Total path cost |
| --- | --- | ---: |
| BFS | S → F → G | 9 |
| A\* | S → B → D → G | 7 |

BFS prioritises the number of edges, whereas A\* uses estimated total cost to guide node expansion. The report also examines admissible heuristics and checks the 8-puzzle calculations with AI feedback.

### Part 2: Applied Machine Learning with AI Copilot

The practical component uses the **California Housing dataset** from scikit-learn to compare **Linear Regression** with **Ridge Regression** at different regularisation strengths.

The notebook performs the following tasks:

1. Load the California Housing dataset and select **1,000 records** using `random_state=42`.
2. Separate the target variable `MedHouseVal` from the eight input features.
3. Apply `StandardScaler` to numerical features.
4. Create an 80%/20% training/test split using `random_state=42`.
5. Evaluate Linear Regression and Ridge Regression with **5-fold cross-validation**, using mean **R²** as the evaluation metric.
6. Compare Ridge penalty values **α = 0.1, 10.0, and 1000.0**.
7. Plot a bar chart of the cross-validation scores.

## Dataset and Features

The prediction target, **`MedHouseVal`**, represents median house value. The eight input features are:

| Feature | Description |
| --- | --- |
| `MedInc` | Median income in the block group |
| `HouseAge` | Median house age |
| `AveRooms` | Average number of rooms per household |
| `AveBedrms` | Average number of bedrooms per household |
| `Population` | Block-group population |
| `AveOccup` | Average household occupancy |
| `Latitude` | Geographic latitude |
| `Longitude` | Geographic longitude |

The dataset is loaded directly through scikit-learn; no separate dataset download is required beyond access to the dataset source when first fetched.

## Model Evaluation Results

The completed report records these **mean 5-fold cross-validation R² scores**:

| Model | Ridge α | Mean CV R² |
| --- | ---: | ---: |
| Linear Regression | — | **0.6457** |
| Ridge Regression | 0.1 | **0.6457** |
| Ridge Regression | 10.0 | **0.6443** |
| Ridge Regression | 1000.0 | **0.3574** |

**Interpretation:** Linear Regression and Ridge Regression with small penalties produced very similar cross-validation scores. Increasing α to 10.0 led to only a small decrease in the reported R² score, whereas α = 1000.0 reduced performance substantially. This illustrates how excessively strong regularisation can cause **underfitting** by shrinking model coefficients too much.

These values are reproduced from the accompanying assignment report; the notebook can be rerun to inspect the output and comparison plot.

## Repository Contents

```text
SC5002-Lab-Assignment/
├── README.md
└── SC5002_Lab_Assignment.ipynb
```

- **`SC5002_Lab_Assignment.ipynb`** — Google Colab notebook containing data preparation, regression model training, cross-validation scores, and the performance comparison chart.
- **`README.md`** — Assignment overview, methods, results, and instructions for running the notebook.

> **Note:** Rename the notebook entry above if your uploaded `.ipynb` file has a different filename.

## How to Run

1. Open [Google Colab](https://colab.research.google.com/).
2. Choose **File → Upload notebook** and upload the `.ipynb` file from this repository, or open the notebook from GitHub within Colab.
3. Select **Runtime → Run all** to execute the notebook.
4. Review the first five dataset rows, model evaluation scores, and the final bar chart.

A Python environment with the libraries below is required. They are typically available in Google Colab:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.datasets import fetch_california_housing
from sklearn.model_selection import train_test_split, cross_val_score
from sklearn.linear_model import LinearRegression, Ridge
from sklearn.preprocessing import StandardScaler
```

## Generative AI as a Learning Assistant

Generative AI was used in the assignment to support understanding and verification rather than replace independent work. The report documents the exact prompts used, explanations in the student's own words, and reflections for five **Learn with AI** tasks:

| Task | AI-assisted activity |
| --- | --- |
| 1.1 | Explain admissible heuristics through a GPS navigation analogy |
| 1.2 | Check manual 8-puzzle A\* calculations and node-selection decisions |
| 2.1 | Identify the continuous prediction target, input features, and purpose of scaling |
| 2.2 | Interpret Linear vs Ridge scores and the value of 5-fold cross-validation |
| 2.3 | Explain why very high Ridge α can lead to underfitting |

## Key Takeaways

- BFS searches by depth, while A\* considers path cost plus a heuristic estimate.
- For the 8-puzzle's misplaced-tile heuristic, **the blank tile should not be counted**.
- Feature scaling puts numerical predictors on comparable scales and is particularly relevant when using coefficient penalties such as Ridge regularisation.
- In this experiment, light regularisation gave results similar to ordinary Linear Regression, but a very large α greatly reduced the mean R² score.
- Cross-validation helps compare models across multiple data partitions rather than relying on a single evaluation split.

## Submission Context

This repository is the **GitHub notebook component** of Task 3.2. The full submission also includes a report (maximum six pages) containing hand calculations, score tables, and AI prompting logs, plus a five-minute video presentation as specified in the assignment instructions.

## Author

**Student:** [Your name]  
**Matric number:** [Your matric number, if you choose to include it publicly]  
**Course:** SC5002 Artificial Intelligence Fundamentals & Applications  
**Institution:** Nanyang Technological University
