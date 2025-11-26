# Bike Sharing Demand Analysis & Prediction

This repository contains a complete data science workflow for analyzing and predicting demand in a bike-sharing system. The project includes data cleaning, exploratory data analysis (EDA), clustering, machine learning modeling, weather integration, and operational insights such as bike redistribution estimation. All work is contained in the 'project.ipynb` notebook.

---

##  Project Overview

The goal of this project is to understand how people use a bike-sharing system and build prediction models capable of forecasting hourly bike pickups and drop-offs. The project examines temporal demand patterns, clusters stations into meaningful groups, incorporates weather data, and estimates the number of bikes that must be redistributed to keep a station cluster balanced.

---

##  Notebook Workflow

### **1. Data Cleaning**
- Convert timestamps to datetime.
- Remove missing values and irrelevant columns.
- Remove extreme outliers in trip durations (99th percentile filtering).
- Prepare station-level summaries for clustering.

### **2. Exploratory Data Analysis (EDA)**
The notebook explores several demand-related patterns, including:
- Daily and hourly trip volume trends.
- Trip duration distribution.
- Most popular origin and destination stations.
- Time-of-day & weekday/weekend usage differences.

Visualizations help uncover seasonality, peak hours, and general mobility behavior.

### **3. Station Clustering**
- Apply K-Means clustering to group stations by geographic coordinates.
- Remove coordinate outliers to improve clustering quality.
- Visualize station clusters using scatter plots and Folium interactive maps.
- Select one high-demand cluster for focused prediction modeling.

### **4. Feature Engineering**
To prepare the prediction model:
- Generate hourly pickup and drop-off counts.
- Add lag features (1–3 hours).
- Encode time features:
  - hour of day  
  - weekend indicator  
  - peak hours classifier  

### **5. Machine Learning Models**
Several models are trained and evaluated on the selected cluster:

- **Linear Regression**
- **K-Nearest Neighbors (KNN)**
- **Multi-Layer Perceptron (MLPRegressor)**

Models are evaluated using R² and error metrics.  
KNN and MLP outperform Linear Regression and become the preferred models.

### **6. Weather Data Integration**
Weather data (temperature, humidity, wind speed, etc.) is merged with the bike data by date.

The ML pipeline is retrained with weather as additional features.

Results show that weather improves model accuracy and helps explain demand variability.

### **7. Bike Redistribution Analysis**
Using predicted pickups and drop-offs:

- Compute cumulative imbalance of bikes.
- Identify when and where shortages or surpluses occur.
- Estimate how many bikes need to be added or removed to maintain service quality.

This provides operational value for real-world fleet management.

---

##  Key Results
- Demand follows strong hourly and daily patterns.
- Weather conditions significantly influence ridership.
- KNN and MLP models provide strong predictive performance.
- Clustering helps isolate areas with distinct behavior.
- Redistribution modeling identifies imbalance periods.

---

##  Future Improvements
- Incorporate additional weather granularity (hourly data).
- Explore LSTM/GRU deep learning models.
- Build a real-time prediction dashboard.
- Expand prediction beyond one cluster to full system forecasting.
- Add optimization models for automated redistribution planning.

---

##  License
This project is intended for educational and research use.  
Feel free to modify or extend it with attribution.
