# 🌾 Crop Mantra - Intelligent Crop Recommendation System

## 📖 Project Overview

**Crop Mantra** is an intelligent web-based crop recommendation system that leverages machine learning to help farmers and agricultural enthusiasts make data-driven decisions about crop selection. The system analyzes soil and environmental parameters to predict the most suitable crop for optimal yield.

Agriculture in India is livelihood for a majority of the population and can never be underestimated. However, the agricultural sector is going through the most stressed phase in the last three decades. Indian agriculture is plagued by several problems; some of them are natural and some others are manmade. Nearly three-quarters of India's families depend on rural incomes. Every solution if rightly executed can make a huge difference.

## 🎯 Problem Statement

Farmers often struggle with choosing the right crop for their land based on soil conditions, weather patterns, and environmental factors. Wrong crop selection leads to:
- Poor yield quality
- Financial losses
- Soil degradation
- Inefficient resource utilization

## 💡 Solution

Our ML-powered web application analyzes multiple agricultural parameters and recommends the most suitable crop, ensuring:
- **Higher crop yield**
- **Better resource utilization**
- **Data-driven farming decisions**
- **Sustainable agriculture practices**

## 🔬 Dataset Information

The system uses a comprehensive agricultural dataset with **2,200 samples** containing:

### Input Features (8 parameters):
1. **N (Nitrogen)** - Nitrogen content in soil (0-140 kg/ha)
2. **P (Phosphorus)** - Phosphorus content in soil (5-145 kg/ha)
3. **K (Potassium)** - Potassium content in soil (5-205 kg/ha)
4. **Temperature** - Average temperature (8.8°C - 43.7°C)
5. **Humidity** - Relative humidity (14% - 99%)
6. **pH** - Soil pH level (3.5 - 9.9)
7. **Rainfall** - Annual rainfall (20mm - 298mm)
8. **Water Usage** - Derived feature (Low/Medium/High) based on rainfall

### Output:
**22 Different Crops** including:
- **Cereals**: Rice, Maize
- **Pulses**: Chickpea, Kidney beans, Pigeon peas, Moth beans, Mung bean, Black gram, Lentil
- **Fruits**: Pomegranate, Banana, Mango, Grapes, Watermelon, Muskmelon, Apple, Orange, Papaya, Coconut
- **Cash Crops**: Cotton, Jute, Coffee

## 🤖 Machine Learning Model

### Algorithm: **Random Forest Classifier**
- **Estimators**: 500 trees
- **Criterion**: Entropy
- **Train-Test Split**: 70-30
- **Features**: 8 input parameters

### Model Performance:
- **Training Data**: 1,540 samples
- **Testing Data**: 660 samples
- **Accuracy**: High performance on crop classification

### Data Preprocessing:
1. **Missing Value Handling**:
   - P, K: Filled with 0 (nutrient deficiency)
   - Numerical features: Mean imputation
   - Categorical features: Mode imputation

2. **Feature Engineering**:
   - Water Usage categorization based on rainfall:
     - Low: ≤150mm
     - High: >250mm
     - Medium: 150-250mm

3. **Encoding**: Label encoding for categorical features

## 🏗️ System Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   User Input    │ -> │  Flask Web App  │ -> │  ML Model       │
│  (8 parameters) │    │  (app.py)       │    │  (model.pkl)    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │  Crop Prediction│
                       │  & Web Response │
                       └─────────────────┘
```

## 📁 Project Structure

```
crop-analysis/
├── 📄 app.py                    # Flask web application
├── 📄 model.py                  # ML model training script
├── 📄 model.pkl                 # Trained ML model (serialized)
├── 📊 plant(IBM - Z).csv        # Dataset (2,200 samples)
├── 📋 requirements.txt          # Python dependencies
├── 🗂️ templates/
│   └── 📄 index.html           # Web interface template
├── 🗂️ static/
│   └── 🎨 css/
│       └── 📄 style.css        # Web styling
├── 📓 Crop Mantra.ipynb        # Jupyter notebook analysis
├── 📄 README.md                # Project documentation
└── 📄 Procfile                 # Deployment configuration
```

## 🚀 Installation & Setup

### Prerequisites
- Python 3.7+
- pip package manager

### Step-by-step Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/ajaymehta369/crop-analysis.git
   cd crop-analysis
   ```

2. **Create virtual environment**
   ```bash
   python -m venv .venv
   .venv\Scripts\activate  # Windows
   # source .venv/bin/activate  # Linux/Mac
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Train the model** (if model.pkl doesn't exist)
   ```bash
   python model.py
   ```

5. **Run the application**
   ```bash
   python app.py
   ```

6. **Access the application**
   - Open browser and navigate to: `http://127.0.0.1:5000`

## 🎮 Usage Instructions

1. **Open the web application** in your browser
2. **Input the following parameters**:
   - Nitrogen content (N)
   - Phosphorus content (P) 
   - Potassium content (K)
   - Temperature (°C)
   - Humidity (%)
   - Soil pH level
   - Rainfall (mm)
   - Water Level/Usage
3. **Click "Predict"** button
4. **View the recommended crop** for optimal yield

## 📊 Test Values for Model Testing

Here are some sample test cases you can use:

### 🌾 Rice Prediction:
```
N: 90, P: 42, K: 43, Temperature: 20.8, Humidity: 82, pH: 6.5, Rainfall: 203, Water Level: 2
Expected Output: rice
```

### 🌽 Maize Prediction:
```
N: 78, P: 52, K: 48, Temperature: 22.5, Humidity: 65, pH: 6.2, Rainfall: 76, Water Level: 1
Expected Output: maize
```

### 🫘 Chickpea Prediction:
```
N: 40, P: 58, K: 20, Temperature: 25, Humidity: 55, pH: 7.2, Rainfall: 45, Water Level: 0
Expected Output: chickpea
```

### ☕ Coffee Prediction:
```
N: 61, P: 38, K: 55, Temperature: 24, Humidity: 76, pH: 6.8, Rainfall: 180, Water Level: 2
Expected Output: coffee
```

### 🍌 Banana Prediction:
```
N: 100, P: 75, K: 50, Temperature: 27, Humidity: 80, pH: 6.0, Rainfall: 120, Water Level: 1
Expected Output: banana
```

## 🛠️ Technologies & Tools Used

### Backend Technologies:
- **Python 3.x** - Core programming language
- **Flask** - Web framework for API development
- **scikit-learn** - Machine learning library
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Pickle** - Model serialization

### Frontend Technologies:
- **HTML5** - Web structure
- **CSS3** - Styling and responsive design
- **Jinja2** - Template engine

### Development Tools:
- **Jupyter Notebook** - Data analysis and experimentation
- **Git & GitHub** - Version control
- **Virtual Environment** - Dependency management

### Machine Learning Stack:
- **Random Forest** - Classification algorithm
- **Label Encoder** - Categorical data encoding
- **Train-Test Split** - Model validation

## 🌟 Key Features

- ✅ **Real-time Crop Prediction**
- ✅ **User-friendly Web Interface**
- ✅ **22 Different Crop Classifications**
- ✅ **High Accuracy ML Model**
- ✅ **Responsive Design**
- ✅ **Easy Parameter Input**
- ✅ **Instant Results**

## 🔮 Future Enhancements

- [ ] **Weather API Integration** for real-time weather data
- [ ] **Soil Testing Kit Integration** for precise soil analysis
- [ ] **Regional Crop Database** for location-specific recommendations
- [ ] **Yield Prediction** along with crop recommendation
- [ ] **Mobile Application** for field use
- [ ] **Multi-language Support** for regional farmers
- [ ] **Historical Data Analysis** and trends
- [ ] **Market Price Integration** for profit optimization

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit changes (`git commit -am 'Add new feature'`)
4. Push to branch (`git push origin feature/new-feature`)
5. Create Pull Request

## 📧 Contact

**Project Maintainer**: Ajay Mehta
- GitHub: [@ajaymehta369](https://github.com/ajaymehta369)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Made with ❤️ for sustainable agriculture and better farming decisions** - get the perfect crop yield 
