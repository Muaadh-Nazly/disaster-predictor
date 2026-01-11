# Model Training

## 📋 Overview

This directory contains the machine learning model training notebooks for three disaster types: **Flood**, **Cyclone**, and **Landslide**. Each disaster type has its own subdirectory with training notebooks and datasets.

## 📁 Structure

```
Modelling/
├── Flood/
│   ├── Model Flood.ipynb      # Flood model training
│   └── Model Flood.csv        # Flood training dataset
├── Cyclone/
│   ├── Model Cyclone.ipynb    # Cyclone model training
│   └── Model Cyclone.csv      # Cyclone training dataset
└── Landslide/
    ├── Model Landslide.ipynb  # Landslide model training
    └── Model Landslide.csv    # Landslide training dataset
```

## 🎯 Models Implemented

For each disaster type, two machine learning models are trained:

1. **Random Forest Regressor (RFR)**
   - Ensemble learning method
   - Handles non-linear relationships
   - Provides feature importance

2. **XGBoost Regressor (XGB)**
   - Gradient boosting framework
   - High performance on structured data
   - Built-in regularization

## 🔄 Training Workflow

### Common Steps (All Models)

1. **Data Loading**
   - Load preprocessed dataset
   - Separate features and target

2. **Feature Encoding**
   - Encode categorical variables using LabelEncoder
   - Apply district and location mappings
   - Handle temporal features

3. **Data Splitting**
   - Train-test split (typically 80-20)
   - Maintain temporal consistency if needed

4. **Model Training**
   - Train Random Forest model
   - Train XGBoost model
   - Tune hyperparameters

5. **Model Evaluation**
   - Calculate metrics (MSE, MAE, RMSE)
   - Compare model performance
   - Analyze feature importance

6. **Model Saving**
   - Save trained models as `.pkl` files
   - Export to Integration directory

## 📊 Model-Specific Details

### Flood Model
- **Target Variable:** Flood occurrence/severity
- **Key Features:** Rainfall, Location, District, Temporal features
- **Output Files:**
  - `Flood_RFRModel.pkl`
  - `Flood_XGBModel.pkl`

### Cyclone Model
- **Target Variable:** Cyclone occurrence/severity
- **Key Features:** Wind Speed, Location, District, Temporal features
- **Output Files:**
  - `Cyclone_RFRModel.pkl`
  - `Cyclone_XGBModel.pkl`

### Landslide Model
- **Target Variable:** Landslide occurrence/severity
- **Key Features:** Rainfall, Location, District, Temporal features
- **Output Files:**
  - `Landslide_RFRModel.pkl`
  - `Landslide_XGBModel.pkl`

## 🛠️ Technology Stack

- **Language:** Python 3
- **Libraries:**
  - `pandas` - Data manipulation
  - `numpy` - Numerical computations
  - `scikit-learn` - Random Forest, metrics, preprocessing
  - `xgboost` - XGBoost implementation
  - `joblib` - Model serialization

## 🚀 Usage

### Training a Model

1. **Navigate to disaster directory**
   ```bash
   cd Modelling/Flood  # or Cyclone, Landslide
   ```

2. **Open the notebook**
   ```bash
   jupyter notebook "Model Flood.ipynb"
   ```

3. **Execute cells sequentially**
   - Load and prepare data
   - Train models
   - Evaluate performance
   - Save models

4. **Copy models to Integration**
   ```bash
   cp *.pkl ../../Integration/
   ```

## 📈 Evaluation Metrics

Models are evaluated using:
- **Mean Squared Error (MSE)** - Penalizes large errors
- **Mean Absolute Error (MAE)** - Average prediction error
- **Root Mean Squared Error (RMSE)** - Standard deviation of residuals

## 🔍 Feature Engineering

### Temporal Features
- Month (1-12)
- Day of month (1-31)
- Seasonal indicators

### Location Features
- District (encoded)
- Location hierarchy (Location, Location1, Location2)
- Geographic encoding

### Weather Features
- Rainfall (for Flood and Landslide)
- Wind Speed (for Cyclone)
- Historical averages

## 📝 Model Files

Trained models are saved as pickle files (`.pkl`) and stored in:
- Training directory (for reference)
- `Integration/` directory (for API use)

## ⚠️ Important Notes

- **Mapping Consistency:** Use same mapping files as preprocessing
- **Model Versioning:** Keep track of model versions
- **Feature Alignment:** Ensure features match preprocessing output
- **Evaluation:** Always evaluate on test set before deployment

## 🔗 Dependencies

### Required Packages
```python
pandas
numpy
scikit-learn
xgboost
joblib
```

### Import Statements
```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.preprocessing import LabelEncoder
from sklearn.metrics import mean_squared_error, mean_absolute_error
from xgboost import XGBRegressor
import joblib
```

## 📊 Model Performance

Each model provides:
- Training performance metrics
- Test performance metrics
- Feature importance rankings
- Prediction capabilities for 4-day horizon

