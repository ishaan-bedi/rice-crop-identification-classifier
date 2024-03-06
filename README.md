# Rice Crop Discovery Tool

## Overview

The Rice Crop Discovery Tool is a project that combines satellite data from Sentinel-1 with machine learning techniques to identify and predict the presence of rice crops in a specific region of Vietnam. Leveraging the capabilities of the Planetary Computer API, this tool provides a systematic approach to gather, process, and model data for informed decision-making in agriculture.

## Project Structure

### 1. Load_PredictionData.ipynb and Load_TrainData.ipynb

#### Purpose:

- **Environment Setup**: Import necessary packages and set up the Planetary Computer API key.
- **Data Collection**: Retrieve rice crop presence data for the year 2020 from a defined region in Vietnam.
- **Sentinel-1 Data Retrieval**: Extract VV and VH band values for a specific location and time frame, essential for predicting rice crop presence.
- **Feature Engineering**: Measure phenology (growth) of rice crops by using statistical combinations of these bands to generate RVI (Radar Vegetation Index).
- **Data Combination**: Merge response (crop presence) and predictor variables (VV, VH) into a unified dataset.
- **Data Storage**: Save the combined dataset for further processing.

### 2. ML_Processing.ipynb

#### Purpose:

- **Data Loading**: Load the combined dataset generated in `Extract_Load.ipynb`.
- **Feature Selection**: Choose relevant columns for model building, focusing on VV and VH variables.
- **Data Splitting**: Divide the dataset into training and testing sets for model evaluation.
- **Feature Scaling**: Utilize Standard Scaler to normalize VV and VH variables.
- **Model Training**: Develop machine learning models, including Logistic Regression, Random Forest, Neural Networks, Naive Bayes, Gradient Boosting, Decision Trees, and K-Nearest Neighbors.
- **In-Sample Evaluation**: Assess model performance on the training dataset through classification reports and confusion matrices.
- **Out-Sample Evaluation**: Predict on the test set to evaluate model generalization, providing accuracy metrics.

## Usage

### Prerequisites

1. Install dependencies listed in each notebook.
2. Obtain a Planetary Computer API key and set it in the notebooks for data access.

### Instructions

1. **Data Preparation**: Execute "Load_PredictionData.ipynb" and "Load_TrainData.ipynb" to collect and prepare the necessary data.
2. **Modeling and Evaluation**: Proceed to "ML_Processing.ipynb" for machine learning model development and evaluation.

Refer to the notebook comments for additional tips and insights during execution.

## Reference and Acknowledgement: 
Parts of the code for this project are adapted from the "benchmark Notebook" provided by "EY Open Science Data Challenge 2024" where the goal of the challenge was to predict the presence of rice crops at a given location using satellite data. This project was submitted to EY as a part of the same challenge.
