# Overview

This project involved working with a large dataset of 2.2 million records and 150 columns. Through preprocessing, the feature set was reduced by approximately 65%, significantly optimizing the data without sacrificing model performance.

## Modeling Techniques

- **LazyPredict**: Initially attempted but failed due to memory overload, likely caused by the dataset size and default unlimited tree depth. Refining LazyPredict would have required extensive customization, making manual model building more practical.
- **Random Forest**: Tested but yielded negligible results.
- **XGBoost (Extreme Gradient Boosting)**: Proved to be the most effective. Its ability to handle class imbalance natively provided a major advantage, eliminating the immediate need for oversampling techniques like SMOTE.

## Observations

The results aligned well with real-world predictors of default risk:

### Strong Indicators
- Payment method (e.g., direct pay)
- Verification status
- Number of accounts opened in the last 24 months

### Weaker Indicators
- Interest rate: Reflects borrower risk but demonstrated limited direct predictive power.
- Debt-to-income ratio: Ranked around the 50th percentile in feature importance, less impactful than anticipated.

## Recommendations

- Apply **SMOTE** or other synthetic oversampling techniques to address class imbalance more thoroughly.
- Revisit and engineer new features, particularly combinations that could enhance predictive power.
- Reevaluate the necessity of features like **interest rate**, which may not independently provide significant signal.

## Future Work

- Feature engineering to create new derived variables.
- Hyperparameter tuning of XGBoost for further optimization.
- Experimenting with additional ensemble methods for potential performance gains.

---

> *This project provided valuable insights into handling large datasets and reinforced the importance of method selection and preprocessing in machine learning pipelines.*
