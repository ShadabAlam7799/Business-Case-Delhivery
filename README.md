# Delhivery – Feature Engineering for Logistics Delivery Time Prediction

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)  
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)  
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-yellow)  
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-blue)  
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-ML%20Preprocessing-green)  
![Feature Engineering](https://img.shields.io/badge/Feature%20Engineering-Transformation%2C%20Encoding-brown)  
![Logistics Analytics](https://img.shields.io/badge/Logistics%20Analytics-Delivery%20Optimization-crimson)  
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-red)  
![Seaborn](https://img.shields.io/badge/Seaborn-Statistical%20Graphics-teal)

---

## Overview
This project focuses on **feature engineering** for **Delhivery**, one of India’s largest logistics and supply chain companies. The goal is to transform raw shipment and operational data into meaningful predictive features to accurately estimate **delivery time**—a critical metric for customer satisfaction, route optimization, and fleet management.

## Problem Statement
Delhivery faces challenges in:
- Providing accurate **estimated time of arrival (ETA)** to customers  
- Handling variability due to geography, traffic, weather, and operational bottlenecks  
- Reducing late deliveries and improving first-attempt success rates  

High-quality features derived from transactional and spatio-temporal data are essential to power robust machine learning models for delivery prediction.

## Solution Approach
This notebook demonstrates a complete **feature engineering pipeline** tailored to logistics data, including:
- Parsing and enriching datetime fields (e.g., day of week, hour of day, holiday flags)  
- Calculating **geospatial distances** between origin and destination (Haversine)  
- Creating **historical performance features** (e.g., avg. delivery time by route, hub, or pincode)  
- Encoding categorical variables (e.g., vehicle type, warehouse ID) using target-aware methods  
- Binning and scaling numerical features (e.g., package weight, distance tiers)  
- Deriving **lag-based operational metrics** (e.g., packages handled in last 24h at origin hub)

*Note: This project focuses exclusively on feature creation—not model training—producing a dataset ready for regression or time-series modeling.*

## Project Structure
```
delhivery-feature-engineering/
├── Project 6 - Business Case - Delhivery - Feature Engineering.ipynb  # Main notebook
├── data/
│   └── shipment_data.csv                # Raw logistics dataset (orders, timestamps, locations)
├── output/
│   └── engineered_features.csv          # Final feature-rich dataset for modeling
├── README.md                            # This documentation
└── requirements.txt                     # Python dependencies
```

## Key Techniques Implemented
- **Temporal Feature Extraction**: Hour, weekday, month, weekend/holiday indicators  
- **Geospatial Engineering**: Distance (km), origin/destination clusters, city-tier mapping  
- **Aggregate Features**: Rolling averages of delivery times by route/hub/pincode  
- **Categorical Handling**: Frequency and target encoding for high-cardinality IDs  
- **Scaling & Normalization**: For distance, weight, and time-based features  
- **Data Leakage Prevention**: Strict time-based splitting during feature creation  

## Technical Requirements
- Python 3.8+  
- Jupyter Notebook  
- Libraries:
  - pandas
  - numpy
  - scikit-learn
  - matplotlib
  - seaborn
  - geopy (or custom Haversine implementation)

## Installation
1. Clone or download the project  
2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```
3. Launch Jupyter Notebook:  
   ```bash
   jupyter notebook
   ```

## Usage
1. Open `Project 6 - Business Case - Delhivery - Feature Engineering.ipynb`  
2. Run cells in sequence to:  
   - Load raw shipment data  
   - Perform exploratory analysis  
   - Engineer temporal, geospatial, and operational features  
   - Export the final engineered dataset (`engineered_features.csv`)  

This output can be directly used to train models (e.g., XGBoost, LightGBM, or neural networks) for **delivery time prediction**.

## Business Impact
- Enables **accurate ETAs** for end customers via apps and SMS  
- Supports **dynamic route planning** and resource allocation  
- Reduces **delivery exceptions** and improves SLA compliance  
- Enhances **customer trust** and retention in a competitive logistics market

## Future Enhancements
- Integrate real-time traffic and weather APIs  
- Add features from delivery attempt history  
- Implement feature store for production pipelines  
- Use embedding techniques for location IDs (e.g., pincode2vec)

## License
This project is for educational and demonstration purposes only. The dataset is synthetic or anonymized. Not intended for production deployment without validation.

---

*Developed as part of a logistics analytics case study*  
*Last updated: November 2025*
