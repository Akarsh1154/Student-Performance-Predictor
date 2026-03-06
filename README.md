# 🎓 ScoreIQ — Student Exam Performance Predictor

A beginner Machine Learning project that predicts a student's exam score based on study habits, attendance, and sleep patterns using Linear Regression.

---

## 📌 Problem Statement

Can we predict how well a student will perform in an exam based on their daily habits?
This project uses realistic student data to train a Linear Regression model that estimates exam scores based on study hours, attendance percentage, sleep hours, and previous grade.

---

## 📊 Dataset Description

The dataset was manually created to simulate realistic student behavior.

| Feature | Description |
|---|---|
| `study_hours` | Number of hours the student studies per day |
| `attendance_pct` | Percentage of classes attended |
| `sleep_hours` | Number of hours of sleep per night |
| `prev_grade` | Previous exam grade (added in Task 5) |
| `exam_score` | Final exam score out of 100 (Target) |

- **Total Rows:** 20 students
- **Total Features:** 4 input features + 1 target column
- **Missing Values:** None
- **Data Types:** All integer (int64)

---

## 🔍 Data Exploration

| Check | Result |
|---|---|
| Shape | (20, 4) |
| Missing Values | 0 in all columns |
| Data Types | int64 across all columns |

---

## 📈 Data Visualization

Three visualizations were created:

- **Scatter Plot** — Study Hours vs Exam Score
- **Histogram** — Distribution of Exam Scores
- **Boxplot** — Spread of Student Attendance Percentage

---

## 🤖 Model Used

**Linear Regression** from `scikit-learn`

- **Training Set:** 80% (16 students)
- **Test Set:** 20% (4 students)
- **Random State:** 42

---

## 📉 Results — Task 4 (Baseline)

| Metric | Score |
|---|---|
| Mean Absolute Error (MAE) | 2.2286 |
| R² Score | 0.9880 |

The MAE of 2.23 means the model's predictions are off by about 2 marks on average out of 100, which is very accurate. The R² of 0.988 means the model explains 98.8% of the variance in exam scores, indicating an excellent fit.

---

## 🧪 Feature Experiment — Task 5

| Round | Features Used | MAE | R² |
|---|---|---|---|
| Baseline | study_hours, attendance_pct, sleep_hours | 2.2286 | 0.9880 |
| Without sleep_hours | study_hours, attendance_pct | 2.2856 | 0.9877 |
| With prev_grade | study_hours, attendance_pct, sleep_hours, prev_grade | 2.1769 | 0.9884 |

**Conclusion:** Removing `sleep_hours` barely changed performance, meaning it is the least important feature. Adding `prev_grade` slightly improved the model, making it the most valuable additional feature. `study_hours` and `attendance_pct` are the core predictors.

---

## ⚠️ Overfitting Check — Task 6

| Version | MAE | R² |
|---|---|---|
| No Train-Test Split | 0.5867 | 0.9982 |
| Proper 80/20 Split | 2.2286 | 0.9880 |

**What is Overfitting?**
Overfitting happens when a model learns the training data too closely — memorizing patterns instead of learning general ones. The no-split version shows a near-perfect MAE of 0.59 because the model is tested on data it already trained on, which is not a fair evaluation. The proper split gives a realistic score of 2.23, which is the true performance on unseen data.

---

## 🏁 Conclusion

This project showed that Linear Regression can accurately predict student exam scores from simple daily habit data. Study hours and attendance percentage were the strongest predictors. The feature experiment confirmed that `prev_grade` adds value while `sleep_hours` has minimal impact. The overfitting check demonstrated why train-test splitting is essential for honest model evaluation.

---

## 🛠️ Libraries Used

- `pandas` — Data creation and manipulation
- `matplotlib` — Data visualization
- `seaborn` — Enhanced visualizations
- `scikit-learn` — Model training and evaluation
