# JAMBOREE ADMISSION PREDICTOR

This project predicts the **probability of admission** into graduate programs abroad based on academic scores and student profile attributes. The dataset used is associated with **Jamboree**, a study-abroad consultancy, and was provided as a part of institutional training.

The objective of this project is to identify which factors most strongly influence admission chances, and to build a **stable and interpretable regression model** to estimate a student's **Chance of Admit**.

---

##  Objective
To develop a regression-based model that predicts the **Chance of Admit (0–1)** using:
- Academic Performance (GRE, TOEFL, CGPA)
- Profile Strength (SOP, LOR)
- University Rating
- Research Experience

---

##  Dataset Description

| Feature | Description |
|--------|-------------|
| GRE Score | Graduate Record Examination score |
| TOEFL Score | English proficiency exam score |
| CGPA | Undergraduate academic performance (0–10 scale) |
| University Rating | University selectivity score (1–5) |
| SOP | Statement of Purpose strength (1–5) |
| LOR | Letter of Recommendation strength (1–5) |
| Research | 1 = Research Experience, 0 = No Experience |
| Chance of Admit | Probability of Admission (0–1) |

---

##  Key Insights from EDA

- **CGPA, GRE, and TOEFL** show the **strongest positive correlation** with admission probability.
- **SOP, LOR, and University Rating** also contribute positively but have **smaller impact**.
- Students with **research experience** show a slightly higher admission probability.
- Most applicants in this dataset have **medium-to-high** admission chances.

---

##  Modeling

| Model | Role |
|-------|------|
| Linear Regression | Baseline prediction model |
| Ridge Regression (L2 Regularization) | Final model to handle multicollinearity |

### Why Ridge Regression?
GRE, TOEFL, and CGPA are **highly correlated** indicators of academic capability.  
Instead of removing them, **Ridge Regression reduces coefficient sensitivity**, improving model stability while retaining interpretability.

---

## Model Performance

| Model | R² Score | Interpretation |
|-------|----------|----------------|
| Linear Regression | ~0.82 | Strong fit & predictive ability |
| Ridge Regression | ~0.82 | Same accuracy, more stable coefficients ✅ |

> **Ridge Regression is selected as the final model.**

---

##  Feature Influence (Ridge Coefficients)

```
CGPA > GRE Score > TOEFL Score > LOR > SOP > University Rating > Research
```

**Conclusion:**  
Academic strength is the **primary driver**, while profile documents and research background provide **supportive influence**.

---

##  Summary
The model explains approximately **82%** of the variation in admission probability. 
Ridge Regression was selected as the final model because it stabilizes the coefficients 
while allowing key academic metrics (GRE, TOEFL, CGPA) to remain in the prediction pipeline. 
This makes the model both **interpretable** and **practically useful** for admission guidance.

---

##  Tech Stack
Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy

---

## How to Run
```bash
pip install -r requirements.txt
jupyter notebook

