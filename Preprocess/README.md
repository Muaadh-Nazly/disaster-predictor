# Data Preprocessing

## 📋 Overview

This directory contains the data preprocessing pipeline for the disaster prediction system. The preprocessing notebook handles data cleaning, feature engineering, and dataset preparation for model training.

## 📁 Contents

### Notebooks
- **Preprocess.ipynb** - Main preprocessing notebook with complete data pipeline

### Input Datasets
- **Original Dataset.csv** - Historical disaster data (up to 2014)
- **New Dataset.csv** - Recent disaster data (2014-2020)
- **Combined Dataset.csv** - Merged dataset from original and new sources

### Processed Datasets
- **Preprocessed.csv** - Final cleaned dataset
- **Model Flood.csv** - Flood-specific dataset for model training
- **Model Cyclone.csv** - Cyclone-specific dataset for model training
- **Model Landslide.csv** - Landslide-specific dataset for model training

### Feature Engineering Outputs
- **Rainfall_Average.csv** - Average rainfall calculations
- **Rainfall_Daily_Average.csv** - Daily average rainfall
- **Wind_Average.csv** - Average wind speed calculations

### Mapping Files
- **District_Mapped.txt** - District name to encoded value mappings
- **Location_Mapped.txt** - Location name to encoded value mappings

## 🔄 Preprocessing Pipeline

### 1. Data Loading
- Load original dataset (pre-2014)
- Load new dataset (2014-2020)
- Combine datasets for comprehensive coverage

### 2. Data Cleaning
- Handle missing values
- Standardize column names
- Fix data type inconsistencies
- Remove duplicates

### 3. Feature Engineering
- Extract temporal features (year, month, day)
- Calculate weather averages (rainfall, wind)
- Create location hierarchies
- Encode categorical variables

### 4. Dataset Creation
- Create disaster-specific datasets
- Filter relevant features for each disaster type
- Prepare data for model training

### 5. Data Export
- Save processed datasets
- Export mapping files for model consistency
- Generate feature engineering outputs

## 🛠️ Key Operations

### Column Renaming
- Standardize column names across datasets
- Map to consistent naming conventions
- Handle special characters and encoding

### Temporal Feature Extraction
- Extract year, month, day from dates
- Create seasonal indicators
- Handle date format variations

### Weather Data Processing
- Calculate rainfall averages
- Compute wind speed averages
- Handle missing weather data

### Location Encoding
- Map district names to codes
- Map location names to codes
- Create hierarchical location structure

## 📊 Data Structure

### Input Format
- Disaster type
- Date information
- Location details (Region, District, Commune)
- Weather parameters

### Output Format
- Encoded categorical features
- Numerical features
- Temporal features
- Target variables

## 🚀 Usage

### Running the Preprocessing

1. **Open the notebook**
   ```bash
   cd Preprocess
   jupyter notebook Preprocess.ipynb
   ```

2. **Execute cells sequentially**
   - Data loading
   - Data cleaning
   - Feature engineering
   - Dataset creation
   - Data export

3. **Verify outputs**
   - Check processed CSV files
   - Validate mapping files
   - Review data quality

## 📝 Output Files

### Model Training Datasets
- **Model Flood.csv** - Used in `Modelling/Flood/`
- **Model Cyclone.csv** - Used in `Modelling/Cyclone/`
- **Model Landslide.csv** - Used in `Modelling/Landslide/`

### Mapping Files
- **District_Mapped.txt** - Used in model training and API
- **Location_Mapped.txt** - Used in model training and API

### Feature Files
- **Rainfall_Daily_Average.csv** - Used in mobile app
- Weather averages for feature engineering

## ⚠️ Important Notes

- Mapping files must be consistent across preprocessing, modelling, and integration
- Processed datasets should be validated before model training
- Feature engineering outputs are used in multiple components
- Date formats must be standardized across all datasets

## 🔗 Dependencies

- `pandas` - Data manipulation
- `numpy` - Numerical operations
- `matplotlib` - Visualization
- `seaborn` - Statistical visualization
- `sklearn.preprocessing` - Label encoding

