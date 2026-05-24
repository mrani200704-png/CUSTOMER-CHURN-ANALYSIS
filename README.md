Project Overview

This project is a Customer Churn Analysis System developed using Python.
It generates a large banking customer dataset and performs:

Data generation
Data analysis
Churn analysis
Statistical reporting
Data visualization

The project helps analyze customer behavior and identify factors that may influence customer churn.

Features
Generate synthetic customer banking data
Analyze customer churn patterns
Perform statistical analysis
Visualize customer behavior
Create correlation heatmaps
Study customer demographics and financial information
Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Libraries Required

Install required libraries:

pip install pandas numpy matplotlib seaborn
Dataset Information

The dataset contains 100,000 customer records.

Column Name	Description
Customer_ID	Unique customer ID
Age	Customer age
Gender	Male/Female
Tenure	Years with bank
Balance	Account balance
CreditScore	Customer credit score
EstimatedSalary	Estimated salary
NumOfProducts	Number of bank products
IsActiveMember	Active membership status
Churn	Customer churn status
Project Workflow
1. Import Libraries
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
Library Usage
Library	Purpose
Pandas	Data handling
NumPy	Random data generation
Matplotlib	Visualization
Seaborn	Advanced plotting
2. Generate Customer Dataset
np.random.seed(42)

n = 100000

Creates a reproducible dataset with 100,000 customers.

Dataset Creation
data = pd.DataFrame({
    "Customer_ID": np.arange(1, n+1),
    "Age": np.random.randint(18, 70, n),
    "Gender": np.random.choice(["Male", "Female"], n),
    "Tenure": np.random.randint(0, 11, n),
    "Balance": np.random.randint(0, 200000, n),
    "CreditScore": np.random.randint(300, 900, n),
    "EstimatedSalary": np.random.randint(10000, 150000, n),
    "NumOfProducts": np.random.randint(1, 5, n),
    "IsActiveMember": np.random.choice([0, 1], n),
    "Churn": np.random.choice([0, 1], n)
})
Data Analysis
3. Display First 5 Rows
print(data.head())

Displays sample customer records.

4. Check Missing Values
print(data.isnull().sum())

Checks for null or missing data.

5. Check Data Types
print(data.dtypes)

Displays datatype of each column.

6. Statistical Summary
print(data.describe())

Provides:

Mean
Standard deviation
Minimum
Maximum
Percentiles
7. Churn Analysis
Count Churned Customers
print(data["Churn"].value_counts())

Shows:

Customers who stayed
Customers who left
8. Age-wise Churn Analysis
print(data.groupby("Age")["Churn"].mean())

Analyzes churn behavior across different age groups.

Data Visualizations
1. Churn Count Bar Chart
data["Churn"].value_counts().plot(kind='bar')
plt.title("Churn Count")
plt.show()

Displays total churn distribution.

2. Age Distribution Histogram
plt.hist(data["Age"])
plt.title("Age Distribution")
plt.show()

Shows customer age distribution.

3. Balance vs Churn Scatter Plot
plt.scatter(data["Balance"], data["Churn"])
plt.title("Balance vs Churn")
plt.show()

Analyzes relationship between:

Customer balance
Churn behavior
4. Correlation Heatmap
sns.heatmap(data.corr(numeric_only=True), annot=True)
plt.show()

Displays correlation between numerical features.

Sample Banking Analytics Visualizations
Key Insights
Customer churn patterns can be identified using banking data.
Customer balance may influence churn behavior.
Age and credit score can impact customer retention.
Correlation analysis helps detect important business relationships.
Data visualization improves understanding of customer trends.
Applications

This project can be used in:

Banking systems
Customer retention analysis
Business intelligence
Financial analytics
Data science projects
Machine learning systems
Future Improvements
Add churn prediction using Machine Learning
Use Logistic Regression or Random Forest
Build interactive dashboards
Add customer segmentation
Deploy as a web application
Use real-world banking datasets
Conclusion

This Customer Churn Analysis System demonstrates how Python can be used to:

Generate large-scale customer datasets
Analyze churn behavior
Perform statistical analysis
Visualize customer trends

The project provides a strong foundation for customer analytics and predictive modeling in banking and finance systems.
