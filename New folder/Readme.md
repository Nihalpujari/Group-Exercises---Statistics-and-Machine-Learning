House Price Prediction: Advanced Regression Analysis
#### Group Members
#### Member 1: Namrata Bhoyar
#### Member 2: Nihal Sarvagnya Pujari
#### Member 3: Anuj Kamble
#### Member 4: Gourav sathegala somanna
#### Member 5: Pramodkumar Shivanna

#### Project Overview
This project performs an end-to-end regression analysis on the Ames Housing Dataset, a comprehensive collection of residential property data from Ames, Iowa. Originally sourced from a popular Kaggle competition, the goal of this study is to predict the final SalePrice of homes by analyzing structural attributes and quality metrics.
Our pipeline moves beyond simple linear estimation, incorporating advanced feature selection, outlier mitigation, and non-linear transformations to uncover the hidden drivers of real estate valuation.

#### Technical Workflow
1. Preprocessing & Data Cleaning
Missing Value Imputation: Utilized median strategies to handle numerical gaps without introducing bias.
Outlier Management: Implemented the IQR method and spatial filtering (GrLivArea < 4000 sqft) to prevent model skewness.
Feature Scaling: Applied StandardScaler to normalize features, ensuring spatial dimensions and year counts are on the same magnitude for the regression weights.
2. Modeling & Evaluation
Linear Regression: Established a baseline model to understand global trends.
Regularization: Integrated Lasso Regression to perform automatic feature shrinkage and prevent overfitting.
Polynomial Ridge: Captured non-linear interactions between home quality and square footage using degree-2 transformations and L2 regularization.
Validation: All models were evaluated using 5-Fold Cross-Validation, R² Score, and Root Mean Squared Error (RMSE).
3. Feature Selection & Enhancement
Used Recursive Feature Elimination (RFE) to isolate the three most impactful predictors of house value.
Visualized feature importance through coefficient magnitude analysis.

#### Key Insights & Visualizations
Feature Impact: Our analysis confirms that "Overall Quality" and "Above Ground Living Area" are the strongest predictors of price.
Error Analysis: Residual plots were utilized to verify the homoscedasticity of our errors, proving that the model remains robust across different price points.

#### Acknowledgments
Data Source: Kaggle "House Prices: Advanced Regression Techniques".
Tools: Python, Pandas, Scikit-Learn, Matplotlib, Seaborn.