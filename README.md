# 🔥 Forest Fire Weather Index (FWI) Predictor

A machine learning web application that predicts the **Fire Weather Index (FWI)** — a numeric indicator of wildfire risk — from meteorological inputs, with an interactive Flask front-end.
---

## 📌 What is FWI?

The **Fire Weather Index (FWI)** is a globally recognized system for rating fire intensity based on daily weather conditions. It is used by forest fire management agencies to assess danger levels and deploy resources proactively.

This project trains and deploys a regression model on the [Algerian Forest Fires Dataset (UCI)](https://archive.ics.uci.edu/dataset/547/algerian+forest+fires+dataset) to predict FWI scores from user-provided weather inputs.

---

## ✨ Features

- 🌡️ Predict FWI from 9 weather parameters (temperature, humidity, wind, rain, etc.)
- 🌐 Clean web UI built with Flask and HTML/CSS
- 🔁 Compared multiple regression models — Ridge Regression selected for deployment
- 📊 EDA and feature engineering in Jupyter Notebooks
- 🧪 StandardScaler used for feature normalization
- 🧠 Trained model serialized with `pickle` for fast inference

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3.8+ |
| Web Framework | Flask |
| ML Library | Scikit-learn |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Notebooks | Jupyter |
| Model Serialization | Pickle |

---

## 📂 Project Structure

```
flask-fwi-prediction/
│
├── notebooks/
│   └── EDA_and_Model_Training.ipynb   # Exploratory analysis + model comparison
│
├── templates/
│   ├── index.html                     # Input form
│   └── result.html                    # Prediction output page
│
├── static/
│   └── style.css                      # Styling
│
├── app.py                             # Flask application entry point
├── ridge_model.pkl                    # Trained Ridge Regression model
├── scaler.pkl                         # Fitted StandardScaler
├── requirements.txt
└── README.md
```

---

## 📊 Dataset

**Algerian Forest Fires Dataset** — UCI ML Repository  
- **244 instances** across 2 regions: Bejaia (NE Algeria) & Sidi Bel-abbes (NW Algeria)  
- **Period:** June–September 2012  
- **Target:** FWI (continuous) for regression; fire/no-fire for classification  

### Input Features Used

| Feature | Description |
|---|---|
| `Temperature` | Max temp (°C) |
| `RH` | Relative Humidity (%) |
| `Ws` | Wind speed (km/h) |
| `Rain` | Total rainfall (mm) |
| `FFMC` | Fine Fuel Moisture Code |
| `DMC` | Duff Moisture Code |
| `DC` | Drought Code |
| `ISI` | Initial Spread Index |
| `BUI` | Buildup Index |

---

## 📈 Model Comparison

| Model | R² Score | MAE |
|---|---|---|
| Linear Regression | ~0.97 | — |
| **Ridge Regression** ✅ | **~0.98** | **Best** |
| Lasso Regression | ~0.97 | — |
| ElasticNet | ~0.96 | — |

> Ridge Regression selected for deployment due to best generalization and lowest error.

---

## ⚙️ Setup & Run Locally

### 1. Clone the repository
```bash
git clone https://github.com/prerna-m01/flask-fwi-prediction.git
cd flask-fwi-prediction
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate        # On Windows: venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the app
```bash
python app.py
```

Open your browser at `http://localhost:5000`

---

## 🖥️ How It Works

1. User fills in the weather parameters on the form
2. Flask receives the POST request and extracts form values
3. Inputs are scaled using the pre-fitted `StandardScaler`
4. Ridge Regression model predicts the FWI score
5. Result is displayed on the output page

---

## 📦 requirements.txt

```
flask
scikit-learn
pandas
numpy
matplotlib
seaborn
pickle5
```

---

## 🎓 Key Learnings

- End-to-end ML pipeline: raw data → cleaning → EDA → feature engineering → training → deployment
- Model evaluation and selection using R² score and MAE
- Serializing and loading ML models with `pickle`
- Building and deploying Flask web apps with form-based input

---

## 📜 Dataset Source

[Algerian Forest Fires Dataset — UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/547/algerian+forest+fires+dataset)

---

## 👤 Author

**Prerna Mishra**  
[GitHub](https://github.com/prerna-m01) 
