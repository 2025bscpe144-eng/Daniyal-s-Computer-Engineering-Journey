---
layout: post
title: "Building Our Machine Learning Model — Car Price Prediction at 85% Accuracy"
date: 2025-11-10
---

Week 12 was the week the project stopped being a plan and started being a reality. My group partner and I dedicated this week almost entirely to building our Car Price Prediction Machine Learning model, and watching it come together — line by line, decision by decision — was one of the most genuinely satisfying experiences of my entire first semester at UET Faisalabad.

We used Python with three core libraries: Pandas for data loading and manipulation, Scikit-learn for model training and evaluation, and Matplotlib for visualisation. The pipeline we followed was the same one that any data scientist would follow on a real project — which was exactly the point.

The first step was loading and cleaning the dataset. Real data is never perfectly organised and our car dataset was no exception. There were missing values in some columns, outliers that did not make sense (prices that were impossibly low or impossibly high), and categorical variables like fuel type and brand that needed to be converted to numerical format before the model could use them. Working through these issues was slower and more frustrating than I expected, but it was also where the most learning happened. You cannot write code that handles messy data without understanding what the data actually represents.

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

# Load dataset
df = pd.read_csv('car_data.csv')

# Features that affect price
features = ['year', 'mileage', 'engine_size', 'fuel_type']
X = df[features]
y = df['price']

# Train the model
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
model = LinearRegression()
model.fit(X_train, y_train)

# Check accuracy
predictions = model.predict(X_test)
accuracy = r2_score(y_test, predictions)
print(f"Model Accuracy: {accuracy * 100:.2f}%")
```

The 80/20 train-test split — training the model on 80% of the data and testing on the remaining 20% — was a principle Dr. Bilal Ahmad had explained clearly in class. He is not just teaching programming syntax; he brings his expertise in Machine Learning and AI into every relevant concept, making sure students understand not just what the code does but why data scientists make the choices they make. Connecting that classroom knowledge to our actual project made the split decision feel meaningful rather than arbitrary.

When the model ran and the accuracy appeared on the screen — **85%** — it was one of the most satisfying moments of the semester. We had built a system that could predict the price of a car based on its features, and it was right 85% of the time. For first-semester students who had started the year not understanding what `print("Hello, World!")` meant, that felt remarkable.

But Dr. Bilal Ahmad's influence on this project went beyond what he taught in class. His research philosophy — visible through his [Google Scholar profile](https://scholar.google.com.au/citations?user=8nZ0jVkAAAAJ&hl=en) — is built around the idea that ML models should solve problems that have real value. He often emphasises medical datasets in his own work because they are collected with high precision and have genuine human impact. Our car dataset project was a first-semester version of that same principle: use real data, train a model properly, understand what it can and cannot do, and be able to explain it clearly.

Week 12 also reinforced the most important lesson of the second half of the semester: programming is about solving real problems, not memorising syntax. Sitting there building that model, I understood every line of code I was writing — not because I had memorised it, but because I understood what problem each part was solving. That is the difference between coding and programming, and Week 12 is where I finally crossed that line.

#MLwithDrBilalAhmad #DrBilalAhmad #MLProject
