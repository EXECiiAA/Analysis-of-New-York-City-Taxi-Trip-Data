# NYC Taxi Tip Prediction
Project Purpose
This project showcases the development of a machine learning pipeline for predicting taxi trip tip amounts using the New York City Taxi Trip Dataset (2020–2023). The project includes data preprocessing, feature engineering, model training, evaluation, and deployment.

Business Case
The goal is to develop a model that predicts taxi trip tips based on trip characteristics such as distance, duration, fare amount, and surcharges. Accurate predictions help:

Enhance customer fare estimations.
Inform driver route optimization.
Contribute to urban mobility insights and policy-making.
Objective
To build a regression model that predicts the amount of the tip (tips) using trip-related features. The initial approach uses linear regression, with plans for further exploration of advanced techniques if needed.

Deliverables
A cleaned dataset stored in a Google Cloud Storage bucket.
Feature-engineered data saved in a /trusted folder in GCS.
A trained regression model saved in the /models folder.
Evaluation metrics summarizing the model's performance.
Python code files for data processing, feature engineering, and modeling.
In the Repository
File Name	Description
EDA.ipynb	Exploratory Data Analysis: Initial insights and visualizations.
data_cleaning.py	Python script for cleaning and standardizing raw data.
model_training.py	PySpark code for feature engineering, model training, and evaluation.
requirements.txt	Dependencies and libraries required to run the project.
project_report.pdf	Detailed project documentation with findings, challenges, and results.
README.md	This file, outlining the project’s purpose, structure, and usage.
Modeling Process
1. Data Cleaning
Loaded raw data from the /landing folder in GCS.
Removed or imputed missing values.
Standardized data types and column names.
Dropped unnecessary columns to streamline processing.
2. Feature Engineering
Derived trip duration using pickup_datetime and dropoff_datetime.
Scaled continuous features like trip_miles, fare_amount, and surcharges.
Assembled key input features into a single vector for modeling.
3. Model Training
Used PySpark’s LinearRegression for simplicity and interpretability.
Target variable: tips.
Features: trip_miles, tolls, sales_tax, congestion_surcharge, trip_duration.
4. Evaluation
Split the dataset into training (80%) and testing (20%).
Evaluated using:
Mean Squared Error (MSE): 5.26
Mean Absolute Error (MAE): 1.33
R-squared (R²): 0.115
5. Outputs
Processed datasets saved in /trusted as Parquet files.
Trained model saved in /models for reuse.
Results
Key Insights
R² of 11.5% indicates room for feature improvement or model selection.
Precision and scalability of PySpark allow for seamless processing of large datasets.
Initial predictions provide a solid baseline for further tuning and experimentation.
Next Steps
Add more contextual features:
Holiday indicator.
Weekday/weekend and time-of-day categorization.
Explore advanced modeling approaches:
Gradient Boosted Trees.
Random Forest Regressor.
Improve feature scaling and outlier handling.
Business Impact
Enhanced Efficiency: Drivers can use tip predictions for better route planning.
Customer Transparency: Improved fare estimations build trust.
Policy Insights: Data analysis supports urban mobility improvements.
