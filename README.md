# NYC Taxi Tip Prediction
**Project Purpose:**

This project showcases the development of a machine learning pipeline for predicting taxi trip tip amounts using the New York City Taxi Trip Dataset (2020–2023). The project spans data preprocessing, feature engineering, model training, evaluation, and deployment.

**Business Case:**

The goal of this project is to develop a model that predicts taxi trip tips based on characteristics such as distance, duration, fare amount, and surcharges. Accurate tip predictions can:

-Enhance customer fare estimations.

-Inform driver route optimization.

-Contribute to insights on urban mobility and policy-making.


**Objective:**

To build a regression model that predicts the amount of the tip using trip-related features. The initial approach utilizes linear regression, with plans to explore advanced techniques as necessary.

**Deliverables:**

-A cleaned dataset stored in a Google Cloud Storage bucket.

-Feature-engineered data saved in the /trusted folder in GCS.

-A trained regression model saved in the /models folder.

-Evaluation metrics summarizing the model's performance.

-Python code files for data processing, feature engineering, and modeling.



**Modeling Process**

**Data Cleaning:**

-Loaded raw data from the /landing folder in GCS.

-Removed or imputed missing values.

-Standardized data types and column names.

-Dropped unnecessary columns to streamline processing.


**Feature Engineering:**

-Derived trip duration using pickup_datetime and dropoff_datetime.

-Scaled continuous features like trip_miles, fare_amount, and surcharges.

-Assembled key input features into a single vector for modeling.


**Model Training:**

-Used PySpark’s LinearRegression for simplicity and interpretability.

-Target variable: tips.

-Features: trip_miles, tolls, sales_tax, congestion_surcharge, trip_duration.


**Evaluation:**

-Split the dataset into training (80%) and testing (20%).

-Evaluated using:

  -Mean Squared Error (MSE): 5.706
  
  -Mean Absolute Error (MAE): 1.536
  
  -R-squared (R²): 0.580
  

**Outputs:**

-Processed datasets saved in /trusted as Parquet files.

-Trained model saved in /models for reuse.


**Results and Key Insights:**

-R² of 58% indicates room for feature improvement or alternative model selection.

-The precision and scalability of PySpark allow for seamless processing of large datasets.

-Initial predictions provide a solid baseline for further tuning and experimentation.


**Next Steps:**

-Add more contextual features such as holiday indicators and time-of-day categorization.

-Explore advanced modeling approaches like Gradient Boosted Trees and Random Forest Regressor.

-Improve feature scaling and outlier handling.


**Business Impact:**

-Enhanced Efficiency: Drivers can use tip predictions for better route planning.

-Customer Transparency: Improved fare estimations build trust and transparency with customers.

-Policy Insights: Data-driven insights support improvements in urban mobility and transportation policies.
