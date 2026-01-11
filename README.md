# Disaster Prediction and Early Warning System

## 📋 Project Overview

A comprehensive prediction model and early warning system for **Flood, Cyclone, and Landslide** disasters in Sri Lanka. This system empowers social resilience by providing timely predictions and safety information to the general public through a mobile application.


## 🎯 Project Objectives

- Predict flood, cyclone, and landslide occurrences in Sri Lanka
- Provide early warning alerts to common people
- Enable proactive disaster preparedness
- Empower social resilience through accessible technology

## 🏗️ System Architecture

The project consists of four main components:

1. **Data Preprocessing** - Data cleaning and feature engineering
2. **Model Training** - Machine learning model development
3. **API Integration** - Backend service for predictions
4. **Mobile Application** - Android app for end users

## 📁 Repository Structure

```
DSGP/
├── Preprocess/              # Data preprocessing and cleaning
│   ├── Preprocess.ipynb    # Main preprocessing notebook
│   └── [Data files]        # Processed datasets
├── Modelling/               # Model training notebooks
│   ├── Flood/              # Flood prediction models
│   ├── Cyclone/            # Cyclone prediction models
│   └── Landslide/          # Landslide prediction models
├── Integration/             # Flask API backend
│   ├── app.py              # Flask application
│   ├── Model_*.py          # Model prediction modules
│   └── *.pkl              # Trained model files
└── MyApplication/          # Android mobile application
    └── app/                # Android app source code
```

## 🛠️ Technology Stack

### Data Science & Machine Learning
- **Language:** Python 3
- **Libraries:**
  - `pandas` - Data manipulation
  - `numpy` - Numerical computations
  - `scikit-learn` - Machine learning algorithms
  - `xgboost` - Gradient boosting framework
- **Models:** Random Forest Regressor, XGBoost Regressor

### Backend API
- **Framework:** Flask
- **Deployment:** Heroku
- **Functionality:** RESTful API for predictions

### Mobile Application
- **Platform:** Android
- **Language:** Java
- **IDE:** Android Studio
- **Backend Services:** Firebase
- **Features:** Real-time predictions, location-based alerts, weather integration

## 🚀 Getting Started

### Prerequisites
- Python 3.7+
- Jupyter Notebook
- Android Studio (for mobile app)
- Firebase account (for backend services)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd disaster-predictor
   ```

2. **Install Python dependencies**
   ```bash
   cd Integration
   pip install -r requirements.txt
   ```

3. **Open preprocessing notebook**
   ```bash
   cd Preprocess
   jupyter notebook Preprocess.ipynb
   ```

4. **Train models**
   ```bash
   cd Modelling/Flood
   jupyter notebook "Model Flood.ipynb"
   ```

5. **Run Flask API**
   ```bash
   cd Integration
   python app.py
   ```

6. **Build Android App**
   - Open `MyApplication/` in Android Studio
   - Configure Firebase
   - Build and run

## 📊 Workflow

### 1. Data Preprocessing
- Load and combine multiple datasets
- Handle missing values
- Feature engineering
- Create model-ready datasets

### 2. Model Training
- Train Random Forest models
- Train XGBoost models
- Evaluate model performance
- Save trained models

### 3. API Integration
- Load trained models
- Create prediction endpoints
- Deploy to Heroku
- Provide REST API services

### 4. Mobile Application
- Connect to API
- Display predictions
- Show location-based alerts
- Provide safety information

## 🔍 Features

### Prediction Capabilities
- **Flood Prediction** - Based on rainfall, location, and temporal features
- **Cyclone Prediction** - Based on wind speed, location, and temporal features
- **Landslide Prediction** - Based on rainfall, location, and temporal features

### Prediction Horizon
- Current day prediction
- 1-day ahead forecast
- 2-day ahead forecast
- 3-day ahead forecast

### Mobile App Features
- User authentication (Firebase)
- Location-based predictions
- Real-time weather data
- Interactive maps
- Disaster alerts and warnings
- Safety information and guidelines

## 📈 Model Performance

Each disaster type uses two models:
- **Random Forest Regressor (RFR)** - Ensemble learning approach
- **XGBoost Regressor (XGB)** - Gradient boosting approach

Both models provide predictions for comparison and ensemble decision-making.

## 🌐 API Endpoints

### Flood Prediction
```
POST /predict_flood
Parameters: Location, Location1, Location2, District, Rainfall(mm)
Returns: Predictions for current day + 3 days ahead (RFR and XGB)
```

### Cyclone Prediction
```
POST /predict_cyclone
Parameters: Location, Location1, Location2, District, Wind Speed(mph) (current + 3 days)
Returns: Predictions for current day + 3 days ahead (RFR and XGB)
```

### Landslide Prediction
```
POST /predict_landslide
Parameters: Location, Location1, Location2, District, Rainfall(mm)
Returns: Predictions for current day + 3 days ahead (RFR and XGB)
```

## 📱 Mobile Application

### Key Activities
- **MainActivity** - Home screen
- **FloodActivity** - Flood predictions
- **CycloneActivity** - Cyclone predictions
- **LandslideActivity** - Landslide predictions
- **MapActivity** - Interactive maps
- **LoginActivity/RegisterActivity** - User authentication
- **AboutUsActivity** - Project information

### Features
- User registration and login
- Location-based services
- Real-time predictions
- Weather data integration
- Interactive disaster maps
- Safety guidelines


## 📚 Dependencies

### Backend (Integration/)
```
flask
numpy
scikit-learn
pandas
joblib
datetime
xgboost
gunicorn
```

### Data Science (Preprocess & Modelling)
```
pandas
numpy
scikit-learn
xgboost
matplotlib
seaborn
joblib
```

## 🔧 Configuration

### Model Files
Trained models are stored as `.pkl` files:
- `Flood_RFRModel.pkl` / `Flood_XGBModel.pkl`
- `Cyclone_RFRModel.pkl` / `Cyclone_XGBModel.pkl`
- `Landslide_RFRModel.pkl` / `Landslide_XGBModel.pkl`

### Mapping Files
- `District_Mapped.txt` - District encoding mappings
- `Location_Mapped.txt` - Location encoding mappings

## 📝 Usage

### Making Predictions via API

```python
import requests

# Flood prediction example
response = requests.post('https://your-api-url/predict_flood', data={
    'Location': 'Colombo',
    'Location1': 'Western',
    'Location2': 'Colombo',
    'District': 'Colombo',
    'Rainfall(mm)': 150.5
})

predictions = response.json()
```

### Mobile App Usage
1. Register/Login to the app
2. Allow location permissions
3. Select disaster type (Flood/Cyclone/Landslide)
4. View predictions for your location
5. Check 3-day forecast
6. View safety guidelines

## 🌍 Impact

This system aims to:
- **Save Lives** - Early warning enables evacuation
- **Reduce Damage** - Proactive preparation
- **Empower Communities** - Accessible technology
- **Build Resilience** - Data-driven disaster management

