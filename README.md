Learnings:
Data Leakages: erro when data when the information from outside the training data or future is incorrectly includeded in the training process. (Basically when models cheats during the training))
Post-hoc flags: A feature(Column) in training data whose value will only gets updated or created once the target event happened. 

# Lead Scoring & Conversion Prediction System
## Business Problem
X Education, an online course provider, gets many leads from
website visits, forms and referrals, but only ~38% become paying
students. Sales reps have limited time, so calling every lead
equally wastes effort and delays contact with high-intent leads.

## Objective
Predict the probability that a lead converts, and rank leads so
the sales team contacts the most promising ones first.

## Users and decision
- **User:** admissions/sales team lead
- **Decision supported:** which leads to call first, and which
  low-probability leads to deprioritise or move to automated nurture

## Success metrics
- Primary: Lift and recall in the top 30% of ranked leads
- Secondary: PR-AUC (Precision-Recall), ROC-AUC (Receiver Operating Characteristic)
- Business: estimated net profit vs. contacting leads at random

## Assumptions (illustrative, not from the dataset)
- Team capacity: can contact 30% of leads
- Cost per lead contact: Rs 100
- Revenue per enrolment: Rs 15,000
- Real values would come from the company's finance data.

## Data
- Source: X Education Lead Scoring dataset (Kaggle)
- ~9,240 leads, 37 columns, target = `Converted`

## Known risks
- Leakage: some columns (e.g. tags, lead quality, last activity)
  may be assigned after sales contact. These must be reviewed and
  excluded from a model meant for use before first contact.
- Placeholder "Select" values act as missing data.

## Project plan
1. EDA  2. Cleaning  3. Feature engineering  4. Modelling
5. Business evaluation  6. Explainability  7. API  8. Docker/tests