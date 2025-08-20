# Dataset: x.csv - Credit Card Fraud Detection

## Overview
This dataset contains credit card transactions made by European cardholders in September 2013. It presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

## Dataset Information
- **File Size:** ~105 MB
- **Format:** CSV (Comma-Separated Values)
- **Storage:** Git LFS (Large File Storage)
- **Rows:** 284,807
- **Columns:** 31

## Data Schema
| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| Time | Numeric | Number of seconds elapsed between this transaction and the first transaction in the dataset |
| V1, V2, ... V28 | Numeric | Principal components obtained with PCA (anonymized features) |
| Amount | Numeric | Transaction amount |
| Class | Binary | Response variable (1 in case of fraud, 0 otherwise) |

## Data Source
- **Source:** Kaggle - [Credit Card Fraud Detection Dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud)
- **Original Source:** Machine Learning Group - ULB (Université Libre de Bruxelles)
- **Collection Date:** September 2013
- **Collection Method:** Real credit card transactions from European cardholders
- **License:** Database Contents License (DbCL) v1.0

## Data Quality
- **Missing Values:** No missing values in the dataset
- **Data Range:** Transactions from September 2013 (2 days)
- **Class Distribution:** Highly imbalanced - 99.828% normal transactions, 0.172% fraudulent transactions
- **Known Issues:** Features V1-V28 are anonymized due to confidentiality, making feature interpretation difficult

## Usage
This dataset is used in the following notebooks:
- `Code/equal_quorum.ipynb` - [Fraud detection analysis with equal weighting]
- `Code/weighted_quorum.ipynb` - [Fraud detection with weighted ensemble methods]
- `Code/utils.ipynb` - [Utility functions for data preprocessing and evaluation]

## Loading the Data
```python
import pandas as pd

# Load the dataset
df = pd.read_csv('Data/x.csv')

# Display basic information
print(f"Dataset shape: {df.shape}")
print(f"Columns: {df.columns.tolist()}")
```

## Data Processing Notes
- **Class Imbalance:** Special attention needed due to extreme class imbalance (0.172% fraud cases)
- **Memory Requirements:** ~105 MB file requires adequate RAM for processing
- **Performance Considerations:** Consider sampling strategies or specialized algorithms for imbalanced data
- **Feature Engineering:** Time feature may need transformation, Amount may benefit from normalization
- **Evaluation Metrics:** Use precision, recall, F1-score, and AUC-ROC rather than accuracy due to imbalance

## Related Files
- `Data/README.md` - This file
- `Code/` - Analysis notebooks for fraud detection using ensemble methods
- `References/references.bib` - Academic references related to fraud detection and ensemble methods

## Citation
If you use this dataset, please cite:
```
Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. 
Calibrating Probability with Undersampling for Unbalanced Classification. 
In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015
```

## Acknowledgments
- Dataset provided by the Machine Learning Group at ULB (Université Libre de Bruxelles)
- Available on Kaggle: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

---
*Last updated: [20/08/2025]*
