<div align="center">

# 🏋️‍♂️ AI Personal Trainer
### Smart Exercise Recommendation System

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Random%20Forest-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-orange?style=for-the-badge)

<img src="https://images.unsplash.com/photo-1534438327276-14e5300c3a48?w=1200&h=400&fit=crop" alt="Fitness Banner" width="100%" style="border-radius: 10px;"/>

</div>

---

## 📋 Table of Contents
1. [**Introduction & Objective**](#introduction)
2. [**Dataset Snapshot**](#dataset)
3. [**Exploratory Data Analysis (EDA)**](#eda)
4. [**Feature Engineering & Preprocessing**](#features)
5. [**Model Comparison & Selection**](#modeling)
6. [**Recommendation Engine Logic**](#recommendation)
7. [**Final Results & Demo**](#results)
8. [**Conclusion & Future Steps**](#conclusions)

---

<a id='introduction'></a>
## 🎯 Introduction & Objective

> *"Finding the right exercise is easy. Finding the **most efficient** exercise for your specific goals is the challenge."*

Whether you have a fully equipped gym or just a pair of dumbbells, optimizing your workout for maximum caloric burn can be a guessing game. This project removes the guesswork by building an **AI-Powered Exercise Recommendation Engine**.

### 💡 The Solution
Instead of generic advice, this system uses **Machine Learning** to:
1.  **🔍 Filter** a massive library of exercises based on your specific constraints (e.g., *Intermediate level, Back workout, Dumbbells only*).
2.  **🧠 Predict** the exact caloric expenditure for each matching exercise.
3.  **🏆 Rank** and suggest the top 5 most efficient movements for you.

### Why It Matters
* **Smart Planning:** Transitions fitness from "feeling" to "data-driven."
* **Efficiency:** Maximizes results per minute spent working out.
* **Adaptability:** Dynamically adjusts recommendations based on available equipment and skill level.

---

<a id='dataset'></a>
## 📊 Dataset Snapshot

This project is powered by the **Life Style Data** dataset, a robust collection of fitness metrics sourced from Kaggle.

* **📂 Source:** `jockeroika/life-style-data`
* **📏 Size:** 20,000 Rows, 54 Columns
* **🧪 Type:** Structured Tabular Data

### 🗝️ Key Features
We extracted specific features to train our predictive model:

| **Feature Category** | **Description** |
| :--- | :--- |
| **🔥 Target Variable** | `Burns Calories (per 30 min)` |
| **💪 Intensity** | `Sets` (3-5), `Reps` (5-30) |
| **🏷️ Categorical** | `Target Muscle Group`, `Equipment Needed`, `Difficulty Level` |
| **🧬 Anatomical** | `Body Part`, `Type of Muscle`, `Benefit` |

---

<a id='eda'></a>
## 🔍 Exploratory Data Analysis

To ensure model reliability, we performed a comprehensive analysis of the data:

* **Distribution Checks:** Confirmed normal distributions for `Sets` and `Reps`, reflecting realistic workout patterns.
* **Outlier Detection:** Used boxplots to identify and verify calorie burn values, ensuring data integrity.
* **Category Balance:** Verified a balanced distribution across difficulty levels (Beginner to Advanced) and wide coverage of muscle groups to prevent bias.
* **Correlation Analysis:** Heatmaps revealed a moderate positive correlation (0.47) between `Sets` and `Calories`, validating intensity as a key predictor.

---

<a id='modeling'></a>
## 🤖 Model Comparison & Selection

We evaluated three models to find the best predictor for calorie burn:

1.  **Linear Regression**: A baseline model.
2.  **Random Forest Regressor**: A robust ensemble method handling non-linear data.
3.  **Gradient Boosting Regressor**: A high-performance boosting algorithm.

| Model | RMSE (Lower is Better) | R² Score (Higher is Better) | Verdict |
| :--- | :--- | :--- | :--- |
| Linear Regression | 26.16 | 0.24 | Underfitting |
| **Random Forest** | **16.53** | **0.69** | **Selected (Robust)** |
| Gradient Boosting| 16.24 | 0.70 | Excellent |

**Decision:** Random Forest was chosen as the final model due to its strong performance, resistance to overfitting, and stability across diverse data inputs.

---

<a id='recommendation'></a>
## ⚙️ Recommendation Engine Logic

The core system is encapsulated in the `recommend_exercises()` function:

1.  **Input:** Takes user constraints (e.g., *Difficulty="Intermediate", Body Part="Back", Equipment="Dumbbells"*).
2.  **Filter:** Subsets the 20,000-row dataset to find relevant exercises.
3.  **Predict:** Applies the trained Random Forest model to estimate calorie burn for each candidate exercise.
4.  **Rank:** Sorts exercises by predicted efficiency (highest calorie burn first).
5.  **Output:** Returns the top 5 recommendations.

---

<a id='results'></a>
## 🚀 Sample Result

**Scenario**: A user requests an **Intermediate** level **Back** workout using **Dumbbells**.

**AI Recommendation:**
1.  **Kettlebell/Dumbbell Swings** (~357 cal)
2.  **Windshield Wipers** (~357 cal)
3.  **Prone Cobras** (~354 cal)
4.  **Plyo Squats** (~353 cal)
5.  **Dips** (~352 cal)

*The model successfully identified high-intensity compound movements that fit the user's criteria, maximizing efficiency.*

---

<a id='conclusions'></a>
## 🏁 Conclusion & Future Steps

### 🎓 Key Takeaways
This project successfully demonstrates how Machine Learning can personalize fitness planning by moving beyond generic advice to data-driven recommendations.

1.  **Data-Driven Efficiency:** We proved that exercise selection significantly impacts caloric burn. By analyzing features like `Sets`, `Reps`, and `Muscle Group`, we can identify movements that maximize energy expenditure.
2.  **Model Superiority:** Tree-based models (**Random Forest** and **Gradient Boosting**) significantly outperformed Linear Regression, highlighting the non-linear relationship between workout intensity and calories burned.
3.  **Actionable Tool:** The final recommendation engine provides a practical way for users to discover optimal exercises based on their specific constraints (e.g., available equipment or difficulty level).

### 🚀 Future Improvements
To make this system even more powerful, future iterations could include:

* **Personalized User Profiles:** Incorporate user weight, age, and gender into the prediction model for more accurate individual calorie estimates.
* **Real-Time Feedback Loop:** Allow users to rate the suggested exercises to refine future recommendations (Reinforcement Learning).
* **Workout Plan Generation:** Instead of single exercises, generate full 30-60 minute workout routines that balance muscle groups and intensity.
* **Computer Vision Integration:** Use a camera to count reps and ensure proper form in real-time.

---
**Thank you for exploring this AI-Powered Fitness Recommender! 💪**
*Feel free to fork this notebook and adapt it to your own fitness data projects.*
