🏠 Airbnb Listing Price Prediction

This project builds a machine learning regression pipeline to predict Airbnb listing prices using property details and review data.
It focuses on robust data cleaning, feature engineering, outlier handling, and scalable preprocessing using scikit-learn pipelines.

🧠 Problem Statement

Airbnb pricing depends on multiple factors such as:

Property characteristics

Stay duration rules

Review quality and recency

Host and location attributes

The objective is to predict listing price accurately using structured data while handling real-world challenges like:

Missing values

High-cardinality categorical variables

Outliers

Mixed data types

📂 Datasets Used
1. Listings.csv

Contains listing-level details such as:

Price

Minimum / maximum nights

Review scores

Property and host attributes

2. Reviews.csv

Contains review-level data:

Review count

Review dates

Listing references

3. Reviews Data Dictionary

Used for understanding review-related fields.

🛠️ Tech Stack & Libraries

Python

Pandas, NumPy – data manipulation

Scikit-learn

Pipelines

ColumnTransformer

Linear Regression

Joblib – model utilities

🔄 Data Processing Workflow
1. Data Loading

Loaded multiple CSV files with encoding handling

Disabled low-memory warnings for large files

2. Missing Value Handling

Removed rows with missing critical values

Applied imputers during preprocessing:

Mean for numerical features

Constant value ("missing") for categorical features

📉 Outlier Detection & Removal

Outliers were detected using the Interquartile Range (IQR) method on key numerical features:

Price

Nights constraints

Review score metrics

Rows with extreme values were removed to improve model stability.

🔗 Data Merging & Feature Engineering

Aggregated review data:

Number of reviews per listing

Most recent review date

Merged aggregated reviews with listing data using listing_id

Created a consolidated modeling dataset

⚙️ Feature Preprocessing
Numerical Features

Missing values → Mean imputation

Scaling → StandardScaler

Categorical Features

Missing values → Constant imputation

Encoding → OneHotEncoder

High cardinality handling:

Retained top 50 categories

Mapped remaining values to "Others"

Pipeline Architecture

Pipeline + ColumnTransformer

Ensures identical preprocessing during training and inference

📊 Train–Test Split

70% Training

30% Testing

Fixed random state for reproducibility

🤖 Machine Learning Model

Model Used: Linear Regression

Task Type: Regression

Target Variable: price

The model is trained on fully preprocessed numerical data.

📈 Model Evaluation
Metrics Used

R² Score

Performance

R² score indicates how well listing features explain price variability.

Sample predictions are printed to compare actual vs predicted prices.

🔮 Prediction Example

The pipeline supports:

Single listing prediction

Fully automated preprocessing

Real-time inference using raw input features

Example output:

Predicted price for this listing: ₹XXXX.XX

🚀 How to Run

Clone the repository

Install dependencies:

pip install pandas numpy scikit-learn joblib


Update dataset file paths if required

Run the notebook or script sequentially

📌 Project Highlights

✔ End-to-end regression pipeline
✔ Outlier detection using IQR
✔ High-cardinality categorical handling
✔ Scikit-learn Pipelines & ColumnTransformer
✔ Clean separation of preprocessing and modeling
✔ Real-world Airbnb pricing use case

🔮 Future Improvements

Try advanced models (Random Forest, XGBoost)

Log-transform price for better stability

Add location-based clustering

Deploy as a Streamlit or FastAPI app

Add cross-validation & hyperparameter tuning
