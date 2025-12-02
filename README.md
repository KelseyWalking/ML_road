# Machine Learning Road  
This repository is a collection of my machine learning projects, resources, and experiments—documenting my journey into Data Science and applied ML. Please note these are Personal open-source projects, not related to my work projects.

## Purpose
I explore machine learning through fun business and personal projects. I will keep documenting my ideas, step-by-step ML workflows, and learnings as I continue exploring.
Some original data from my past work cannot be used, so I replace them with similar public datasets and build prototype projects using my own ideas.  

## Content
This repo includes projects: pricing optimization frameworks, demande forecasting framework, recommendation framework, and customer clustering models.  

## Project Summary
I hope to summary my thoughts about how to find the solution and how to implementate the ML Framework in one page summary. This will highlight each project's learning and future work. Here is one example of my Price Optimization ML Framework.

Executive Summary

Challenges:
1. The conversion label is defined at the quote level, while the pricing optimization goal operates at the product level (Category, Item).
2. Determine optimal markups that balance conversion probability and profit margin, given the observed strong negative relationship between markup levels and quote conversions.

Solutions:
1. Quote Conversion Modeling
a. Developed a ML model to predict quote conversion probability using strong quote-level and product-level features.
b. The XGBoost model with SHAP interpretation revealed that:
i. Compute Category is highly price-sensitive, indicating that small changes in markup significantly affect conversion.
ii. Quote Type matters: Quote-to-Order (QTO) conversions drop faster with higher markups than Normal Quotes, suggesting stronger price competition for QTO
buyers.
iii. Region: North American quotes exhibit higher conversion rates, reflecting regional pricing and competition patterns.
iv. Timing: Conversions are time-dependent—quotes published later in the week (Friday to Sunday) show higher conversion rates.




3. Pricing Optimization Framework
a. Built an Expected Margin Optimization Framework that integrates the tuned Conversion XGBoost model with a Grid Search engine.
b. The framework simulates multiple product-level markup combinations, predicts conversion probabilities, and identifies the combination that maximizes expected margin
at the quote level.

Results:
1. Model Performance: XGBoost model achieved 88.2% accuracy and AUC = 0.90 on the test set.
<img width="1289" height="731" alt="image" src="https://github.com/user-attachments/assets/51732e3f-6416-4558-9714-d2f321bb57ab" />
2. Optimization Outcome: When applied to a random test quote (simulating a new order):
○ Predicted Conversion Probability increased by 124%.
○ Expected Margin improved by 197%.
<img width="1137" height="638" alt="image" src="https://github.com/user-attachments/assets/a132dbc8-50c0-42ad-83e8-15e82613c1ec" />

<img width="1121" height="609" alt="image" src="https://github.com/user-attachments/assets/58e6a63b-4a29-4f4c-b866-c16168a14156" />


Learnings:
1. This project test and prove a concept that product-level features can effectively serve as quote-level predictors, allowing models like XGBoost to capture how within-quote
variations influence overall conversion probability.
2. SHAP analysis based on XGBoost model provides transparency in understanding which product categories drive conversion changes.
3. The Grid Search approach successfully identifies optimal markup combinations that balance profitability with deal-winning likelihood.

Next steps:
1. Model Enhancement: Explore hierarchical or mixed-effects modeling once more item-level data becomes available to better capture nested relationships between quotes and
products.
2. Business Integration: Collaborate with the sales and pricing teams to:
○ Investigate why current intra-quote markup variations are limited.
○ Incorporate business rules and strategic constraints into the optimization process for real-world deployment.

## Disclaimer
The resources in this repository are for **educational purposes only**.  
Do not use any materials here for commercial purposes.


