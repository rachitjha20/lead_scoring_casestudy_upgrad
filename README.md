
# Lead Scoring Case Study

This repository contains a case study focused on predicting lead conversion for a business using machine learning models. The primary objective is to identify key factors that lead to higher conversions and build a predictive model.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Installation and Setup](#installation-and-setup)
- [Data Preprocessing](#data-preprocessing)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)
- [Model Building](#model-building)
- [Model Evaluation](#model-evaluation)
- [Recommendations](#Recommendations)

---

## Project Overview

In this project, we aim to analyze customer lead data to predict the likelihood of a customer converting. The analysis includes exploratory data analysis (EDA), feature engineering, model building, and evaluation.

## Dataset

The dataset includes information about leads such as their email behavior, source of the lead, current occupation, and activity on the website. Key columns include:

- **Do Not Email**
- **Total Time Spent on Website**
- **Lead Source**
- **Last Activity**
- **Specialization**
- **What is your current occupation?**
- **Last Notable Activity**

## Installation and Setup

To run the notebook and reproduce the analysis, follow these steps:

1. Clone the repository:
    ```bash
    git clone https://github.com/your-repo-name/lead-scoring-case-study.git
    ```

2. Install the necessary dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Open the Jupyter notebook:
    ```bash
    jupyter notebook lead_scoring_case_study.ipynb
    ```

## Data Preprocessing

We performed the following preprocessing steps:

1. **Missing Values Treatment**:
   Missing values in the dataset were handled by either removing them or imputing them with appropriate values.

2. **Feature Encoding**:
   Categorical variables such as `Lead Origin`, `Lead Source`, and `Specialization` were encoded using techniques such as one-hot encoding.

3. **Boolean Conversion**:
   All boolean columns were converted to integers (`0` and `1`).

4. **Feature Scaling**:
   Numerical features were standardized to ensure uniformity across the dataset.

## Exploratory Data Analysis (EDA)

We performed an EDA to understand the distribution of data and identify important patterns.

- **Graph 1**: Distribution of Total Time Spent on Website.

  - ![image](https://github.com/user-attachments/assets/e2366fc3-5de1-41c3-9145-59239b814034)

  _Label: Insert graph showing the distribution of the total time spent on the website._

- **Graph 2**: Conversion rate by Lead Source.


  - ![image](https://github.com/user-attachments/assets/de05ee3d-a60b-49c1-bf2f-00711b078fc1)

  _Label: Insert graph showing the conversion rate for each lead source._

- **Graph 3**: Conversion rate by Last Activity.


  - ![image](https://github.com/user-attachments/assets/92ce425b-19d6-4216-9164-d912b5d4dd4f)

  _Label: Insert graph showing the conversion rate for the last activity performed by leads._

## Model Building

We used the following models to predict lead conversion:

- **Logistic Regression**:
  A baseline model for binary classification tasks.

The final dataset was split into training and testing sets. Recursive Feature Elimination (RFE) was applied for feature selection.

### Code Snippet:
Here’s how RFE was applied to select the most important features:

```python
from sklearn.feature_selection import RFE
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()
rfe = RFE(model, 10)
fit = rfe.fit(X_train, y_train)
```

## Model Evaluation

We evaluated the models using the following metrics:

- Accuracy : 78.61 %
- Sensitivity : 77.18 %
- Specificity : 79.92 %

- **Graph 4**: ROC Curve of the models.


  - ![image](https://github.com/user-attachments/assets/e02cd630-8102-4996-9a1a-e6cf3e04c9ce)

  _Label: Insert ROC curve comparison between models._

## Recommendations:

* The company **should make calls** to the leads coming from the `lead sources "Welingak Websites"`  and `"Reference"` as these are more likely to get converted.
* The company **should make calls** to the leads who are the `"working professionals"` as they are more likely to get converted.
* The company **should make calls** to the leads who spent `"more time on the websites"` as these are more likely to get converted.
* The company **should make calls** to the leads coming from the `lead sources "Olark Chat"` as these are more likely to get converted.
* The company **should make calls** to the leads whose `last activity` was `SMS Sent` as they are more likely to get converted.

* The company **should not make calls** to the leads whose `last activity` was `"Olark Chat Conversation"` as they are not likely to get converted.
* The company **should not make calls** to the leads whose `lead origin` is `"Landing Page Submission"` as they are not likely to get converted.
* The company **should not make calls** to the leads whose `Specialization` was `"Others"` as they are not likely to get converted.
* The company **should not make calls** to the leads who chose the option of `"Do not Email" as "yes"` as they are not likely to get converted.

---


