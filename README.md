<div align="center">

# 🎓 AI Educational Assistant
### *Personalized Learning Through Machine Learning*

**Undergraduate Research Project · UFRRJ**

[![Python](https://img.shields.io/badge/Python-3.13.5-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![Google Colab](https://img.shields.io/badge/Google_Colab-Notebooks-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)](https://colab.research.google.com)
[![Status](https://img.shields.io/badge/Status-In_Development-brightgreen?style=flat-square)]()

</div>

---

## 📌 Overview

This project is an **intelligent tutoring system** built as part of an undergraduate research program at [UFRRJ](https://portal.ufrrj.br/). The goal is to apply machine learning to create a more **personalized and predictive** learning experience for students, identifying at-risk students early and understanding learning patterns before they lead to failure.

We collected, cleaned, and prepared real educational datasets from Computer Science studenta from UFRRJ, then built and tested multiple ML models. This repository documents both our **research findings** and our **learning journey** throughout the process, as well as the development itself.

---

## 🧠 Machine Learning Models

### 🔵 K-Means Clustering
> *Unsupervised learning to discover natural student groupings*

We applied K-Means to cluster students based on their **binary pass/fail profiles** across six courses. Grades were converted to binary values (0 = failed, 1 = passed), allowing the algorithm to identify groups of students with similar academic patterns - without any prior labels.

Key decisions included how to initialize centroids and how to select `k`, since the number of clusters directly impacts the precision and interpretability of results.

**Courses analyzed:** `IM885`, `IM853`, `TN707`, `TN705`, `TN706`, `TN703`

---

### 🟠 K-Nearest Neighbors (KNN)
> *Supervised classification to predict student performance*

We built KNN **from scratch** and benchmarked it against scikit-learn's implementation. The model predicts a student's performance in `TN703` based on their grades in five other courses.

Two classification modes were implemented:

| Mode | Description |
|------|-------------|
| `binary` | 0 = failed (grade < 5) · 1 = passed (grade ≥ 5) |
| `4groups` | 1 = very low · 2 = low · 3 = medium · 4 = high |

Evaluation used confusion matrices, accuracy scores, classification reports, and PCA for 2D visualization of decision boundaries.

---

### 🟢 Naive Bayes
> *Probabilistic classification using Bayes' Theorem*

We implemented **Gaussian Naive Bayes** to predict whether a student will pass or fail *Engenharia de Software*, using grades from other courses as features.
Even though some course grades may be correlated, the algorithm treats features independently - hence *naive*. Despite this simplification, the model achieves solid predictive performance on our dataset.

---

## 🗂️ Project Structure

```
ai-educational-assistant/
│
├── notebooks/
│   ├── 📓 k-means.ipynb
│   ├── 📓 KNN.ipynb
│   └── 📓 naive-bayes.ipynb
│
├── data/
├── requirements.txt
└── README.md
```

> Student IDs have been fully anonymized - replaced with integers to protect privacy.

---

## 🛠️ Technologies

| Tool | Purpose |
|------|---------|
| **Python 3.13.5** | Core language |
| **Pandas** | Data manipulation and preprocessing |
| **NumPy** | Numerical computing |
| **scikit-learn** | ML algorithms, evaluation metrics, PCA |
| **Matplotlib** | Visualizations and decision boundary plots |
| **Google Colab** | Experiments and prototyping |

---

## 📊 Dataset

The dataset contains **anonymized academic records** from Computer Science students at UFRRJ, collected through a Python script from SIGAA. It including grades (0–10) across multiple disciplines. 
Our key preprocessing steps included:

- Handling missing values (`dropna` / `fillna`)
- Grade discretization (binary and 4-class labeling)
- Feature selection based on course codes

---

## 👥 Team

Built by a college research team as part of an undergraduate research program (*Iniciação Científica*) at **UFRRJ - Universidade Federal Rural do Rio de Janeiro**.

<div align="center">
  <a href="https://github.com/d-olivr/ai-educational-assistant/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=d-olivr/ai-educational-assistant" />
  </a>
</div>

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/your-org/ai-educational-assistant.git
cd ai-educational-assistant

# Install dependencies
pip install pandas numpy scikit-learn matplotlib

# Open notebooks in Jupyter or Google Colab
jupyter notebook KNN.ipynb
```

Or open directly in Google Colab by uploading the `.ipynb` files and the dataset.




