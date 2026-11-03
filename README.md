# student-performance-prediction
# Student Performance Prediction

Predicting students' final exam scores (regression) and pass/fail outcome (classification) from study habits and background, using Python and scikit-learn.

## Dataset
UCI Student Performance dataset (Math course), available on Kaggle. 395 students, 33 columns.

## What I Did
- Dropped G1 and G2 (earlier grades) to avoid data leakage, since they almost give away the final grade G3
- One-hot encoded the 17 text columns
- Created a pass/fail label (G3 >= 10 = pass); the data is 265 pass and 130 fail
- Split the data 80/20 into training and test sets
- Compared every model against a simple baseline and used 5-fold cross-validation for a more reliable score

## Results

**Regression (predicting the exact score)**

| Model | MAE (marks out of 20) |
|---|---|
| Baseline (predict the average) | 3.65 |
| Linear Regression | 3.40 |

**Classification (pass/fail)**

| Model | Accuracy | Failing students caught |
|---|---|---|
| Baseline (always predict pass) | 67% | 0% |
| Random Forest | 70% | 24% |
| Logistic Regression (balanced) | 64% | 52% |

## Key Findings
- [Write in your own words: study habits and background alone are weak predictors]
- [Write in your own words: why accuracy is misleading when the classes are imbalanced]
- [Write in your own words: the trade-off between the two classification models]

## What I Would Do Next
- Try the Portuguese-course dataset for more rows
- Test removing students with a final grade of 0, who likely skipped the final exam
- Look at which features matter most

## How to Run
Open the notebook in Google Colab, upload `student_data.csv`, and run all cells.

## Tools
Python, Pandas, NumPy, scikit-learn
