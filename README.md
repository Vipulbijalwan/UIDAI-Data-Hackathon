# UIDAI-Data-Hackathon

1️⃣ Project Overview

Aadhaar is the world’s largest digital identity ecosystem, generating massive volumes of data through enrolment, biometric updates, and demographic updates.
This project analyzes UIDAI-provided datasets to uncover societal trends, regional behaviour, data quality gaps, and operational inefficiencies.

The objective is to transform raw Aadhaar data into actionable insights that can support:

Policy formulation

Administrative planning

Workforce and infrastructure optimisation

This project was developed as part of the UIDAI Data Hackathon / EY-style analytics challenge.

2️⃣ Errors in the Dataset (Data Quality Issues)

The datasets reflect real-world government data challenges, including:

Duplicate records across datasets

Inconsistent state name formats

District naming inconsistencies

Invalid or mismatched pincodes

High-cardinality categorical fields

Examples of inconsistent state names:

dadra and nagar haveli

dadra & nagar haveli

daman & diu

daman and diu

dadra and nagar haveli and daman and diu

These errors required extensive cleaning, standardisation, and validation.

3️⃣ Total Number of Records (Before & After Cleaning)
🔹 Biometric Update Dataset

Total records: 1,861,108

Duplicate records: 94,896

Records after cleaning: 1,766,212

States identified: 57

Districts:

Raw: 950

Cleaned: 750

🔹 Enrolment Dataset

Total records: 1,006,029

Duplicate records: 22,957

Records after cleaning: 983,051

States identified: 54

Districts cleaned: 950 → 750

🔹 Demographic Update Dataset

Total records: 2,071,700

Duplicate records: 473,601

Records after cleaning: 1,598,097

States identified: 64

Districts cleaned: 946 → 750

4️⃣ Error Handling & Data Cleaning Approach

To resolve dataset errors, the following steps were applied:

Merged multiple raw files into consolidated datasets

Removed duplicate records using PySpark

Standardized state names using mapping logic (e.g., Uttaranchal → Uttarakhand)

Fixed district names using an external pincode reference dataset

Added latitude and longitude to all datasets via pincode mapping

Validated record counts after every transformation

Ensured final datasets contained no null values

This process made the data analysis-ready and reliable.

5️⃣ Methodology
5.1 Data Ingestion & Standardisation

Ingested large datasets using Databricks

Combined fragmented files into three master datasets

5.2 Feature Engineering

Created analytical features such as:

State-level aggregation

District-level aggregation

Combined update metrics across age groups

5.3 Analytical Techniques

Univariate, bivariate, and multivariate analysis

Time-series analysis and seasonality detection

Geospatial analysis using maps

Cross-dataset correlation analysis

Anomaly detection for unusual patterns

6️⃣ Data Analysis & Visualisation Highlights
🔹 Enrolment Trends

State-wise enrolment density heatmaps

Abnormal enrolment spikes near Gujarat and West Bengal borders

Lower adult enrolment indicating saturation coverage

🔹 Biometric Update Patterns

State-wise and month-wise update trends

Population-wise update distribution

Identification of low-activity districts

🔹 Demographic Update Behaviour

Migration-heavy districts leading in demographic updates

District-level activity concentration

🔹 Anomaly Detection

Detected anomalies include:

Invalid state/district/pincode records

Unexpected spikes due to migration or administrative drives

Lower activity in tribal belts (Chhattisgarh, Jharkhand, Andhra Pradesh)

7️⃣ Forecasting Results

Strong seasonal patterns identified

Expected workload surges in March, May, and October

Useful for enrolment center capacity planning

8️⃣ Key Insights
Behavioural Insights

Migration-heavy districts dominate demographic updates

Uneven biometric update coverage for children

Enrolment saturation in southern and western states

Operational Insights

Infrastructure gaps in Odisha and Chhattisgarh

Persistent low biometric update activity in specific districts

Social Insights

Rising digital adoption reflected in demographic updates

Higher enrolment in 0–5 age group indicating population growth

9️⃣ Recommendations & Solution Framework
🔹 Integrated Data Validation

Dropdown-based selection of state, district, and pincode

Prevents invalid data entry

🔹 Early-Warning System

Alerts triggered by:

Zero-activity months

40% drops in enrolment or updates

Abnormal spikes or device failure patterns

🔹 Targeted Outreach

Awareness campaigns for child biometric updates

Special drives in migration-heavy districts

🔹 Predictive Capacity Planning

Advance resource allocation before surge months

Workforce and device optimisation

🔟 Tools & Technologies Used

Databricks

PySpark

SQL

Python

Power BI



Folium / Kepler.gl

GitHub (version control)
