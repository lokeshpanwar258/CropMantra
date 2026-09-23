# 🌾 CropMantra - Intelligent Crop Recommendation System

## 📖 Project Overview

**CropMantra** is an intelligent web-based crop recommendation system that uses machine learning to help farmers and agricultural users make data-driven crop selection decisions.

The system analyzes soil and environmental parameters and predicts a suitable crop based on the provided conditions.

## 🎯 Problem Statement

Farmers often struggle with selecting the right crop for their land based on soil conditions, weather patterns, and environmental factors.

Wrong crop selection can lead to:

- Poor yield quality
- Financial losses
- Soil degradation
- Inefficient resource utilization

## 💡 Solution

CropMantra uses a machine learning model to analyze agricultural parameters and recommend a suitable crop.

The system aims to support:

- Better crop selection
- Better resource utilization
- Data-driven farming decisions
- Sustainable agriculture practices

## 🔬 Dataset Information

The system uses an agricultural dataset containing **2,200 samples**.

### Input Features

The model uses the following parameters:

1. **N (Nitrogen)** - Nitrogen content in soil
2. **P (Phosphorus)** - Phosphorus content in soil
3. **K (Potassium)** - Potassium content in soil
4. **Temperature** - Average temperature
5. **Humidity** - Relative humidity
6. **pH** - Soil pH level
7. **Rainfall** - Annual rainfall
8. **Water Usage** - Derived feature based on rainfall

### Output

The system can classify the input into **22 different crops**, including:

- Rice
- Maize
- Chickpea
- Kidney Beans
- Pigeon Peas
- Moth Beans
- Mung Bean
- Black Gram
- Lentil
- Pomegranate
- Banana
- Mango
- Grapes
- Watermelon
- Muskmelon
- Apple
- Orange
- Papaya
- Coconut
- Cotton
- Jute
- Coffee

## 🤖 Machine Learning Model

### Algorithm

**Random Forest Classifier**

Model configuration:

- **Estimators:** 500 trees
- **Criterion:** Entropy
- **Train-Test Split:** 70-30
- **Features:** 8 input parameters

### Model Data

- **Training Samples:** 1,540
- **Testing Samples:** 660

### Data Preprocessing

The project includes preprocessing and feature engineering steps such as:

1. Missing value handling
2. Numerical feature imputation
3. Categorical feature imputation
4. Water usage categorization based on rainfall
5. Label encoding for categorical features

## 🏗️ System Architecture

```text
┌─────────────────┐
│   User Input    │
│  8 Parameters   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Flask Web App │
│     (app.py)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│    ML Model     │
│   (model.pkl)   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Crop Prediction │
│  & Web Response │
└─────────────────┘
📁 Project Structure
CropMantra/
│
├── app.py                  # Flask web application
├── model.py                # ML model training script
├── model.pkl               # Trained ML model
├── plant(IBM - Z).csv      # Agricultural dataset
├── requirements.txt        # Python dependencies
│
├── templates/
│   └── index.html          # Web interface template
│
├── static/
│   └── css/
│       └── style.css       # Web styling
│
├── Crop Mantra.ipynb       # Jupyter notebook
├── CropAnalysis.png        # Project image
├── index.html              # HTML file
├── style.css               # CSS file
├── README.md               # Project documentation
└── .gitignore              # Git ignored files
🚀 Installation & Setup
Prerequisites
Python 3.7+
pip package manager
Git
1. Clone the Repository
git clone https://github.com/lokeshpanwar258/CropMantra.git
cd CropMantra
2. Create a Virtual Environment
Windows
python -m venv .venv
.venv\Scripts\activate
Linux / macOS
python -m venv .venv
source .venv/bin/activate
3. Install Dependencies
pip install -r requirements.txt
4. Train the Model

If model.pkl is not available, train the model using:

python model.py
5. Run the Application
python app.py
6. Open the Application

Open your browser and visit:

http://127.0.0.1:5000
🎮 Usage Instructions
Open the CropMantra web application.
Enter the required agricultural parameters:
Nitrogen
Phosphorus
Potassium
Temperature
Humidity
Soil pH
Rainfall
Water Usage
Click the Predict button.
View the recommended crop.
📊 Sample Test Values
🌾 Rice
N: 90
P: 42
K: 43
Temperature: 20.8
Humidity: 82
pH: 6.5
Rainfall: 203
Water Level: 2

Expected output:

rice
🌽 Maize
N: 78
P: 52
K: 48
Temperature: 22.5
Humidity: 65
pH: 6.2
Rainfall: 76
Water Level: 1

Expected output:

maize
🫘 Chickpea
N: 40
P: 58
K: 20
Temperature: 25
Humidity: 55
pH: 7.2
Rainfall: 45
Water Level: 0

Expected output:

chickpea
☕ Coffee
N: 61
P: 38
K: 55
Temperature: 24
Humidity: 76
pH: 6.8
Rainfall: 180
Water Level: 2

Expected output:

coffee
🍌 Banana
N: 100
P: 75
K: 50
Temperature: 27
Humidity: 80
pH: 6.0
Rainfall: 120
Water Level: 1

Expected output:

banana
🛠️ Technologies & Tools Used
Backend
Python
Flask
scikit-learn
Pandas
NumPy
Pickle
Frontend
HTML5
CSS3
Jinja2
Machine Learning
Random Forest Classifier
Label Encoding
Train-Test Split
Development Tools
Jupyter Notebook
Git
GitHub
Python Virtual Environment
🌟 Key Features
🌱 Machine Learning based crop recommendation
🌾 22 crop classifications
🖥️ User-friendly web interface
📊 Multiple soil and environmental parameters
⚡ Instant prediction results
📱 Responsive web design
🔬 Data preprocessing and feature engineering
🔮 Future Enhancements
Weather API integration
Soil testing kit integration
Regional crop database
Yield prediction
Mobile application
Multi-language support
Historical data analysis
Market price integration
🤝 Contributing

Contributions are welcome.

Fork the repository.
Create a feature branch.
Make your changes.
Commit your changes.
Push the branch.
Create a Pull Request.
📄 License

This project is created for educational and project demonstration purposes.