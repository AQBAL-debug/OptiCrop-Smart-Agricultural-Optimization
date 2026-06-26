# OptiCrop - Smart Agricultural Production Optimization Engine

OptiCrop is an advanced software system that utilizes data-driven insights to optimize agricultural production for different crops. By integrating key environmental factors such as Nitrogen (N), Phosphorous (P), Potassium (K) levels, soil temperature, humidity, pH, rainfall, and crop types, OptiCrop provides intelligent recommendations to farmers for maximizing yields and resource efficiency.

## Features

### Scenario 1: Smart Crop Recommendation for Farmers
Farmers can enter soil and environmental details (N, P, K, temperature, humidity, pH, rainfall) and receive recommendations for the most suitable crop for maximum yield and farming efficiency.

### Scenario 2: Crop Suitability and Environmental Assessment
Users can evaluate whether current soil and climate conditions are suitable for a particular crop, receiving insights about crop compatibility, environmental suitability, and productivity potential.

### Scenario 3: Agricultural Research and Policy Planning
Researchers and policymakers can analyze crop-environment relationships and identify patterns in agricultural production to make data-driven decisions for sustainable farming strategies.

## Dataset

The project uses the Crop Recommendation Dataset from Kaggle, containing 2200 samples with the following features:
- N: Nitrogen content ratio in soil
- P: Phosphorous content ratio in soil
- K: Potassium content ratio in soil
- temperature: Soil temperature in °C
- humidity: Relative humidity in %
- ph: Soil pH value
- rainfall: Rainfall in mm
- label: Crop type (22 different crops)

## Installation & Setup

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### Step 1: Install Dependencies
Install all required packages using the requirements file:
```bash
pip install -r requirements.txt
```

If you encounter any issues, you can install packages individually:
```bash
pip install pandas numpy scikit-learn streamlit plotly matplotlib seaborn joblib
```

### Step 2: Train the Model
Before running the application, you need to train the machine learning model. The training script will:
- Load and preprocess the dataset
- Train a Random Forest Classifier
- Save the trained model and preprocessors

Run the training script:
```bash
python train.py
```

**Expected Output:**
- Dataset information and statistics
- Model accuracy (should be ~99.55%)
- Cross-validation scores
- Feature importance analysis
- Model saved to `models/` directory

### Step 3: Run the Application
Once the model is trained, start the Streamlit web application:
```bash
streamlit run app.py
```

Or if streamlit is not in your PATH:
```bash
python -m streamlit run app.py
```

**The application will open in your browser at:** `http://localhost:8501`

## Usage Guide

### Scenario 1: Smart Crop Recommendation
1. Navigate to the "🌱 Smart Crop Recommendation" tab
2. Adjust the environmental parameter sliders:
   - Nitrogen (N): 0-140
   - Phosphorus (P): 5-145
   - Potassium (K): 5-205
   - Temperature: 0-45°C
   - Humidity: 10-100%
   - Soil pH: 3.5-9.5
   - Rainfall: 20-300mm
3. Click "🔮 Get Crop Recommendation"
4. View the recommended crop with confidence score and top 3 alternatives
5. Review environmental factor analysis

### Scenario 2: Crop Suitability Assessment
1. Navigate to the "🔍 Crop Suitability Assessment" tab
2. Set environmental parameters using the sliders
3. Select a target crop from the dropdown menu
4. Click "🔍 Assess Suitability"
5. View the suitability score, level, and environmental analysis

### Scenario 3: Agricultural Research Dashboard
1. Navigate to the "📊 Agricultural Research Dashboard" tab
2. Explore three analysis tabs:
   - **Crop Distribution**: View distribution of crop samples in the dataset
   - **Environmental Analysis**: Analyze distributions and correlations of environmental factors
   - **Crop-Environment Relationships**: Explore relationships between environmental factors and crops

## Troubleshooting

### "ModuleNotFoundError: No module named 'pandas'"
```bash
pip install pandas numpy scikit-learn
```

### "ModuleNotFoundError: No module named 'streamlit'"
```bash
pip install streamlit plotly
```

### "Error loading the model"
Ensure you have run the training script first:
```bash
python train.py
```

### Streamlit command not found
Use the Python module approach:
```bash
python -m streamlit run app.py
```

### Port 8501 already in use
Run on a different port:
```bash
streamlit run app.py --server.port 8502
```

## Model Performance

- **Algorithm:** Random Forest Classifier
- **Accuracy:** 99.55%
- **Cross-Validation Accuracy:** 99.32% (±0.85%)
- **Dataset Size:** 2,200 samples
- **Number of Crops:** 22 different crop types
- **Features:** 7 environmental parameters (N, P, K, temperature, humidity, pH, rainfall)

**Feature Importance (Top Factors):**
1. Rainfall: 23.0%
2. Humidity: 22.4%
3. Potassium (K): 17.5%
4. Phosphorus (P): 15.1%
5. Nitrogen (N): 9.6%
6. Temperature: 7.2%
7. Soil pH: 5.1%

## Project Structure

```
OptiCrop/
├── data/
│   └── crop_recommendation.csv
├── models/
│   └── crop_recommendation_model.pkl
├── src/
│   ├── data_preprocessing.py
│   ├── model_training.py
│   └── crop_recommendation.py
├── app.py
├── requirements.txt
└── README.md
```

## Model Performance

The system uses a Random Forest Classifier with cross-validation, achieving high accuracy in crop recommendations based on soil and environmental parameters.
