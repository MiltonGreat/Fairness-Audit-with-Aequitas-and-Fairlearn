# Fairness Audit of Loan Approval Models

![screenshot-localhost_8888-2025 04 08-13_30_32](https://github.com/user-attachments/assets/6b6f183a-8f39-407b-a3ea-55b1b512c49e)

### Overview

This project conducts a fairness audit of loan approval prediction models, focusing on gender bias using key fairness metrics:

- Demographic Parity (approval rate fairness)
- Equal Opportunity (qualified applicant approval fairness)
- Disparate Impact (legal 80% rule compliance)
- Equalized Odds (error rate fairness)

I evaluate three models (Logistic Regression, Random Forest, Tuned Random Forest) and implement Fairlearn for bias mitigation.

### Dataset

#### Columns
- Demographics: Gender, Married, Dependents, Education, Self_Employed
- Financials: ApplicantIncome, CoapplicantIncome, LoanAmount, Loan_Amount_Term, Credit_History
- Property: Property_Area (Urban/Rural/Semiurban)
- Target: Loan_Status (Y/N)

### Key Findings

- All models passed the 80% rule (Disparate Impact ≥ 0.8).
- However, all models failed Equalized Odds (differences > 0.2), indicating biased error rates.
- DemographicParity mitigation slightly worsened fairness metrics.
- EqualizedOdds mitigation (recommended) reduced error rate disparities.

### Recommendations

1. Use Tuned Random Forest for best accuracy + fairness balance.
2. Apply EqualizedOdds mitigation to reduce error rate disparities.
3. Monitor fairness quarterly with new data.

### Conclusion

All models failed in Equalized Odds (differences > 0.3), revealing disparities in error rates (False Positives & False Negatives). This suggests that while approvals were fair, mistakes in predictions disproportionately affected one gender.

### Source

[Loan Application Data from Kaggle](https://www.kaggle.com/datasets/vipin20/loan-application-data)
