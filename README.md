# Medical-Insurance-Cost-Prediction
Overview
This project aims to predict individual medical insurance costs based on a set of personal attributes. By leveraging a dataset of insurance beneficiaries, this analysis involves exploratory data analysis (EDA), data cleaning, feature engineering, and the implementation of a Linear Regression model to understand the key factors that influence insurance charges.

The entire analysis is documented in the Jupyter Notebook: Insurance charges pred.ipynb.

Dataset
The project utilizes the insurance.csv dataset, a popular dataset for regression tasks. It contains 1,338 observations with the following columns:

age: Age of the primary beneficiary.

sex: Gender of the beneficiary (male or female).

bmi: Body mass index, providing an understanding of body weight relative to height.

children: Number of children covered by health insurance / Number of dependents.

smoker: Whether the beneficiary is a smoker (yes or no).

region: The beneficiary's residential area in the US (northeast, southeast, southwest, northwest).

charges: Individual medical costs billed by health insurance. (This is the target variable).

Project Workflow
The project follows a standard machine learning workflow:

Exploratory Data Analysis (EDA):

The dataset was loaded and inspected for null values and basic statistics.

Visualizations such as histograms and box plots were used to understand the distribution of numerical features like age, bmi, and charges.

Categorical features like sex, smoker, region, and children were analyzed using count plots.

A correlation heatmap was generated to observe the initial relationships between numerical variables.

Data Cleaning and Preprocessing:

Duplicate entries were identified and removed.

Categorical features were converted into a numerical format:

Label Encoding was applied to binary features (sex and smoker).

One-Hot Encoding was used for the region feature to create separate binary columns for each region.

Feature Engineering & Selection:

A new feature, bmi_category, was created by binning the bmi values into standard weight categories (Underweight, Normal, Overweight, Obese). This was then one-hot encoded.

Key numerical features (age, bmi, children) were scaled using StandardScaler to normalize their range.

Feature importance was assessed using:

Pearson Correlation for numerical features.

Chi-Squared Test for categorical features.

Based on the analysis, a final set of features was selected to train the model, dropping those with low predictive power.

Model Building and Evaluation:

The preprocessed data was split into training (80%) and testing (20%) sets.

A Linear Regression model was trained on the training data.

The model's performance was evaluated on the test set to see how well it generalizes to new data.

Results
The trained Linear Regression model performed well on the unseen test data, explaining a significant portion of the variance in insurance charges.

R-squared Score: 0.804

Adjusted R-squared Score: 0.799

This indicates that approximately 80% of the variability in medical charges can be explained by our model's features. The analysis revealed that being a smoker is the most significant factor in determining higher insurance costs.
