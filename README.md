# Fraud Detection – Data Preprocessing

This project applies basic data preprocessing techniques (missing value handling, scaling, noise handling, outlier detection, and feature selection) to a fraud‑detection transactions dataset.

## Dataset
- **Name:** Fraud Detection Transactions Dataset  

- **Members:** Nihal Sarvagnya Pujari, Namrata Bhoyar, Anuj Kamble, Gourav sathegala somanna, Pramodkumar Shivanna

- **Source:** https://www.kaggle.com/datasets/samayashar/fraud-detection-transactions-dataset  

- **Description:** A realistic transaction-level dataset containing 50,000 records with 21 features including transaction amounts, account balances, risk scores, device types, locations, and merchant categories. The target variable Fraud_Label (0/1) enables fraud prediction modeling. Perfect for preprocessing practice due to mixed numerical/categorical features, potential outliers in amounts, and realistic banking data characteristics.

## Methods
- Missing values: median (numeric) and mode (categorical) imputation

- Scaling: Z‑score standardization and Min–Max normalization Z-score preserves distribution shape but changes scale. Min-Max preserves relationships but is outlier-sensitive. For fraud detection amounts, Z-score is safer since transaction amounts likely have outliers. 

- Noise handling: Gaussian noise + rolling mean smoothing 

- Outliers: We detected outliers in Transaction_Amount using the Z‑score method with a threshold of |z| > 3. This flags values more than three standard deviations away from the mean, which are statistically very unlikely and can overly influence scaling and model training. Because our dataset is large (50,000 rows), removing these few extreme points reduces the impact of abnormal transactions and makes the distribution more stable, without significantly reducing the amount of useful data. In a real fraud‑detection project we would carefully check domain knowledge before dropping rare but meaningful cases, but for this preprocessing exercise removal is a simple and transparent choice.  

- Feature selection: For feature selection we used a filter method based on mutual information between each numerical feature and the target Fraud_Label. Mutual information was chosen because it is model‑independent, fast to compute on a large dataset, and can capture non‑linear relationships between features and the fraud label, unlike simple correlation which only measures linear dependence.