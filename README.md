# CareLoop Clinics — No-Show Guard

## Project Overview

Predict clinic appointment no-shows using Python, SQL,
Machine Learning and Gemini AI.

## Four Key Findings

1. **Python:** 990 cleaned appointments with
   218 no-shows (22.0%).

2. **SQL:** Gomti Nagar Care Point recorded the highest
   no-show rate (33.3%) across 90 appointments.

3. **Machine Learning:** Logistic Regression selected using
   training cross-validation (AUC 0.7737).
   Test ROC-AUC: 0.7889.

4. **GenAI:** 10 notes processed.
   Most frequent validated reason: illness_or_emergency
   (1 notes).

## Business Recommendation

CareLoop Clinics should prioritize evening follow-up calls
for appointments with higher predicted no-show risk.

Across 990 appointments, 218 were no-shows
(22.0%).

Patients booking 31 or more days ahead had a
60.5% no-show rate, compared with
16.2% for bookings made 1–7 days ahead.

Gomti Nagar Care Point recorded a 33.3% no-show rate
across 90 appointments.

The selected Logistic Regression model achieved a test
ROC-AUC of 0.7889.

The clinic should prioritize flagged patients for follow-up
calls and use the GenAI findings to guide conversations.

## Machine Learning Results

| Metric | Result |
|---|---|
| Selected Model | Logistic Regression |
| Training CV ROC-AUC | 0.7737 |
| Test ROC-AUC | 0.7889 |
| Selected Threshold | 0.35 |
| Test Precision | 0.5714 |
| Test Recall | 0.5714 |
| Test Appointments | 198 |
| Appointments Flagged | 49 |

The model was selected using five-fold training
cross-validation. The decision threshold was chosen using
out-of-fold training F1 scores, without using test results.

## GenAI Analysis

Gemini Flash was used to analyse call-centre notes.
Responses were validated using Pydantic.

| Metric | Result |
|---|---|
| Notes Processed | 10 |
| Valid Responses | 4 |
| Invalid Responses | 5 |
| Blank Notes Skipped | 1 |
| Most Common Validated Cause | illness_or_emergency |

## Limitations

1. Only 10 notes were analysed, so their reasons cannot
   represent all clinic no-shows.

2. Cleaning statistics were calculated before splitting
   the data, introducing a small risk of data leakage.

3. The random split can place the same patient in training
   and testing and does not simulate future predictions
   using only historical data.

## Technologies

- Python, pandas, NumPy
- MySQL
- scikit-learn
- Google Gemini API
- Pydantic
- Google Colab

## Security

Gemini API credentials must be supplied at runtime.
No API keys should be committed to GitHub.
