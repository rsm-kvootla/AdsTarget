# Optimal Targeting of Mobile Ads

## Overview
This project analyzes different ad-targeting strategies foR a mobile gaming company, to optimize customer acquisition through an external ad network The goal is to determine the best targeting strategy using **logistic regression** and compare it with existing methods, including the ad network’s proprietary machine learning predictions.

## Project Objectives
1. **Evaluate different targeting strategies**:
   - Spam all prospects
   - Continue with the current targeting approach
   - Use a **logistic regression model** for ad targeting
   - Use **Ad Network’s proprietary predictions**
   - Decide on which approach is better

2. **Perform predictive modeling**:
   - Implement **logistic regression** to predict ad click-through rates (CTR)
   - Assess model performance using metrics like **pseudo R-squared, chi-square test, and permutation importance**
   - Generate **confusion matrices** to evaluate accuracy

3. **Assess financial implications**:
   - Calculate cost-per-impression (CPM), expected customer lifetime value (CLV), and profitability
   - Compare the return on marketing expenditures (ROME) across targeting strategies

4. **Analyze model performance**:
   - Conduct a **decile analysis** to group impressions by predicted CTR
   - Generate **gains curves** to measure cumulative improvement in targeting
   - Address **multicollinearity** and omitted variable bias

## Dataset
The dataset consists of **115,488 impressions** where an ad was served. Each row represents a unique impression and includes:

- **User behavior**: Number of past impressions, past clicks, CTR
- **App & device information**: Mobile OS, app ID
- **Time-based features**: Hour of impression
- **Predictions from Vneta’s model**
- **Outcome variable**: Whether the ad was clicked

### Key Variables:
- `click`: Indicator if the ad was clicked (yes/no)
- `time_fct`: Hour of the impression
- `app`: App ID where the ad was served
- `mobile_os`: Mobile OS of the user
- `ctrua`: Past CTR of the user across all apps
- `pred_vneta`: Click probability predicted by Vneta

## Methodology
### Part I: Logistic Regression
- Train a logistic regression model using historical ad impression data.
- Predict the probability of a user clicking the ad.

### Part II: Multicollinearity & Omitted Variable Bias
- Examine highly correlated features (e.g., `imppat` & `clpat`).
- Compute **Variance Inflation Factors (VIF)** to detect multicollinearity.
- Re-estimate models with and without correlated variables.

### Part III: Decile Analysis
- Rank impressions into **deciles** based on predicted click probabilities.
- Compare the **actual click-through rate (CTR)** in each decile.
- Generate a **bar chart** of CTR by decile.

### Part IV: Gains Curve
- Construct a **gains table** to analyze cumulative improvement.
- Plot a **gains curve** to visualize targeting efficiency.

### Part V: Confusion Matrix
- Generate a confusion matrix for **logistic regression** and **random targeting**.
- Calculate accuracy based on break-even response rate.
- Compare performance between models.

### Part VI: Model Comparison & Profitability Analysis
- Use financial assumptions to calculate **expected profits** for each targeting strategy.
- Compute **return on marketing expenditures (ROME)**.
- Compare performance under different spending scenarios.

## Results & Recommendations
- The logistic regression model is expected to **outperform random targeting** by prioritizing high-CTR users.
- If Vneta’s predictions provide a significantly higher **ROME**, subscribing to their service may be justified.
- The business should consider **additional data acquisition** if it enhances targeting precision.

## Technologies Used
- **Python** (pandas, numpy, scikit-learn, matplotlib)
- **Machine Learning** (Logistic Regression, Feature Engineering, Model Evaluation)
- **Data Visualization** (Seaborn, Matplotlib for Gains Curve, Decile Analysis)

