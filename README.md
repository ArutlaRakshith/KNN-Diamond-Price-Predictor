# KNN-Diamond-Price-Predictor
KNN regression built from scratch to predict diamond price using diamonds dataset.

# KNN-Diamond-Price-Scratch

K-Nearest Neighbors **regression model built fully from scratch** to predict diamond prices on a real-world Diamonds dataset (~54,000 rows). Manual k tuning, proper preprocessing, full iteration on test data, and comparison with sklearn’s in-built KNN show a working, stable.

## KNN Regression Algorithm (How It Works)
1. Manually select a k value (example: k=5)  
2. For each test diamond, compute distance to all train diamonds using Euclidean distance  
3. Sort distances from smallest to largest  
4. Pick top k nearest neighbor prices  
5. Take the mean of those k prices → predicted price  

**Euclidean Distance Formula:**  
`distance = sqrt( sum((x1 - x2)^2) )`

## Dataset & Preprocessing
- Dataset: `diamonds.csv` (mixed numerical + categorical features)  
- Target: `price` (USD 326 – 18823)  
- Train/Test split: 75:25 (using sklearn split, no data leakage)  
- Categorical encoding: One-Hot Encoder (`cut, color, clarity` → 0/1 vectors)  
- Numerical scaling: Standard Scaling (`(x-mean)/std`) for fair KNN distance  

## Model Results (k = 5 chosen manually)
| Model | Predictions | MAE (USD) | RMSE (USD) |
|---|---:|---:|---:|
| Scratch KNN | 13,485 | 591.41 | 1075.82 |
| Sklearn KNN | 13,485 | 591.59 | 1075.64 |

**What This Means:** Predictions count is same for both, errors are close, proving my scratch model works correctly on full test data. MAE ~500-670 USD shows the model predicts diamond prices very close to real market values. RMSE confirms stable performance on large feature ranges.

## Tech Stack / Tools Used
Python, Pandas, NumPy, Matplotlib, OneHotEncoder, StandardScaler, ColumnTransformer, Git, GitHub, Jupyter Notebook. KNN logic written manually using loops, distance ranking, and mean neighbor price prediction (no sklearn KNN used in scratch part).



Eat, Code, Sleep, Repeat.
