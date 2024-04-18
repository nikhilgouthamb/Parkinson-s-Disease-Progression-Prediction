
# Parkinson's Disease Progression Prediction

This project aims to predict the progression of Parkinson's disease using peptide and protein data, along with clinical information. We use a time series forecasting approach with ARIMA models to predict the Unified Parkinson's Disease Rating Scale (UPDRS) scores for different types (UPDRS_1, UPDRS_2, UPDRS_3, UPDRS_4).

## Dataset

The dataset consists of the following files:

- `train_peptides.csv`: Contains peptide abundance data for each patient visit.
- `train_proteins.csv`: Contains protein expression data for each patient visit.
- `train_clinical_data.csv`: Contains clinical information for each patient visit.
- `supplemental_clinical_data.csv`: Contains additional clinical information.

## Data Preprocessing

- Merged peptide and protein datasets based on `visit_id`, `visit_month`, and `patient_id`.
- Merged the combined dataset with clinical data.
- Calculated the sum of peptide abundance per patient visit.
- Calculated the mean protein expression per patient visit.
- Handled missing values in the `updrs_3` and `updrs_4` columns.

## Model Training and Prediction

- Split the data into training and testing sets for each UPDRS type.
- Trained ARIMA models for each UPDRS type using the training set.
- Made predictions for the testing set using the trained models.
- Combined all predictions into a single CSV file for submission.

## Files Included

- `train_peptides.csv`
- `train_proteins.csv`
- `train_clinical_data.csv`
- `submission_v2.7.csv`: Contains the predictions for UPDRS scores.
- `dawr-t1.ipynb`: Contains the code

## Usage

To run the code, make sure you have the required packages installed (see `library` statements in the code). Then, simply run the code in an R environment.

```R
# Load required packages
library(forecast)
library(caret)
library(dplyr)
library(tidyr)
library(lubridate)

# Load and preprocess the data
# (Code snippets for data loading and preprocessing)

# Train the model and make predictions
# (Code snippets for model training and prediction)

# Save the predictions to a CSV file
write.csv(all_predictions, "submission_v2.7.csv", row.names = FALSE)
```

