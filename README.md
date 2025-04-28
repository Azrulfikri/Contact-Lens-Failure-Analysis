# Project Title: Contact Lens Manufacturing Failure Driver Analysis

## 1. Introduction / Overview

This project focuses on analyzing simulated data from a contact lens manufacturing process to develop a predictive model. The primary aim is to identify the key process variables significantly impacting batch yield.
## 2. Problem Statement

Low batch yields in contact lens manufacturing lead directly to increased material wastage and significant financial losses for the business. Compounding this issue, critical process data is often siloed across different stages (e.g., moulding, filling, QC), making comprehensive root cause analysis difficult.
## 3. Goal / Objective

The main objectives of this project were to:
Demonstrate the integration of simulated data from disparate manufacturing process stages.
Develop a predictive model to identify and quantify the key factors driving batch yield variability.
Specifically investigate and validate the impact of pre-delensing storage duration, based on domain knowledge.
Provide data-driven insights to inform potential strategies for yield improvement.
## 4. Data

The data used in this project was **simulated** using Python libraries (Pandas, NumPy), carefully designed to reflect the key stages and potential data points available in a real-world contact lens manufacturing process based on prior domain experience. This involved simulating data typically siloed across different steps:
**Moulding:** Batch/cavity origin identifiers, target power, associated moulding line.
**Filling & Curing:** Relevant dates, monomer information (conceptual).
**Warehousing:** Simulated entry dates allowing for the calculation of storage duration.
**Quality Control:** Simulated Pass/Fail results for key upstream checks (e.g., Mould Dimension, Filling).
**Traceability:** Unique Batch IDs designed to link data across the different simulated stages.
A critical feature engineered for the analysis was **Storage_Duration_Days**, representing the time between warehouse entry (after filling/curing) and the delensing stage. The overall goal of using this data was to understand how these combined features influence indicators of batch success or yield.
## 5. Methodology / Workflow

The project workflow involved the following key stages:
**Data Simulation & Preparation:** Generated structured batch-level data reflecting the multi-stage manufacturing process and potential influencing factors using Pandas and NumPy.
**Data Integration:** Programmatically merged the distinct simulated datasets based on Batch IDs to create a unified analytical dataset, mimicking the process of overcoming real-world data silos.
**Exploratory Data Analysis (EDA):** Conducted initial analysis using Matplotlib and Seaborn to visualize data distributions (e.g., storage duration) and explore potential relationships between input features and yield indicators.
**Feature Engineering:** CalculatedStorage_Duration_Daysbased on simulated dates. Processed categorical features (like QC results) into a numerical format suitable for modeling.
**Modeling:** Applied predictive regression models from the Scikit-learn library to quantify the relationships between the integrated features and batch yield/success indicators.
**Model Evaluation & Interpretation:** Assessed model fit and extracted feature importances to understand key drivers, particularly validating the significance of storage duration.
**Conclusion:** Summarized findings and related them back to potential operational improvements.
*(Add Link to Notebook: [Analysis Notebook](Your_Project1_Notebook_Filename.ipynb))*
## 6. Key Findings & Results

**Storage Duration is Critical:** The analysis, primarily through model feature importances, strongly confirmed that theStorage_Duration_Daysfor filled moulds prior to delensing is the most significant predictor of batch yield/success in this simulated process.
**Risk Threshold Identified:** Batches stored for longer durations, particularly those exceeding approximately **6 months (180 days)**, showed a markedly higher association with failure/lower yield within the model.
**Upstream Factors:** While less dominant than storage time in this analysis, upstream variables like simulated Mould Dimension QC results also showed some predictive value, indicating their contribution to the overall outcome. *(Consider embedding a key visualization if available, e.g., a simplified bar chart showing feature importances with Storage Duration clearly dominant)*
## 7. Conclusions & Business Impact

The primary conclusion from this analysis is that managing the **storage duration** of filled moulds before delensing represents a critical opportunity for improving yield and reducing waste in this specific manufacturing context. The findings provide strong, data-driven justification for implementing or reinforcing operational strategies such as:
**First-In, First-Out (FIFO):** Prioritizing the use of older inventory batches to minimize the time any batch spends in storage, particularly avoiding durations beyond the ~6-month threshold.
**Inventory Optimization:** Using insights like this could inform better coordination between production planning and warehouse management.
By addressing the key factor identified through modeling, the business could potentially achieve significant **cost savings** through reduced material wastage and **increase effective daily output** due to higher batch success rates. This project also underscores the value unlocked by integrating data from different process stages to gain a holistic understanding.
## 8. Technologies Used

Python
Pandas (for Data Manipulation, Simulation)
NumPy (for Numerical Operations, Simulation)
Scikit-learn (for Regression Modeling, Feature Importance)
Matplotlib & Seaborn (for Data Visualization, EDA)
Google Colab (as the development environment)
Git / GitHub (for version control and project hosting)
## 9. Limitations

**Simulated Data:** The most significant limitation is that this analysis relies entirely on simulated data. Findings require validation using actual historical production data.
**Scope of Simulation:** The simulation captured key assumed variables but inevitably simplifies the real-world manufacturing environment.
**Model Focus:** The modeling effort centered on identifying the primary drivers (feature importance) rather than exhaustive hyperparameter tuning.
## 10. Future Work

**Validation with Real Data:** Apply this analytical pipeline to actual historical production data.
**Quantify Financial Impact:** If validated, estimate potential cost savings and yield improvements from optimized storage strategies.
**Explore Secondary Factors:** Conduct deeper analysis into secondary factors identified by the model using real data.
**Refine Simulation:** Enhance simulation with more granularity if real data remains inaccessible
