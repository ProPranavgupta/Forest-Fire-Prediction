# Forest-Fire-Prediction
Forest Fire prediction ML Project

# 🔥 Forest Fire Prediction ML Project

A Machine Learning web application that predicts the **forest fire risk/burned-area-related outcome** based on environmental and weather conditions such as temperature, relative humidity, wind speed, rainfall, FFMC, DMC, and ISI.

The project uses a **Ridge Regression** model and a **Flask** web application to provide predictions through a simple web interface.

---

## 🚀 Project Overview

Forest fires are strongly influenced by environmental and weather conditions. This project uses Machine Learning to analyze these factors and generate a prediction based on user-provided input.

The trained Machine Learning model is integrated into a Flask application where users can enter environmental parameters and receive a prediction.

### Key Features

- 🔥 Forest fire prediction using Machine Learning
- 🤖 Ridge Regression model
- 🌡️ Weather and environmental feature-based prediction
- 🐍 Python-based ML implementation
- 🌐 Flask web application
- 📊 Scikit-learn preprocessing
- 💾 Saved ML model using Pickle
- 🖥️ Simple and user-friendly interface

---

## 🛠️ Technologies Used

| Technology       | Purpose                   |
| ---------------- | ------------------------- |
| Python           | Programming language      |
| Flask            | Web application framework |
| NumPy            | Numerical operations      |
| Pandas           | Data processing           |
| Scikit-learn     | Machine Learning          |
| Ridge Regression | Prediction model          |
| StandardScaler   | Feature scaling           |
| HTML/CSS         | Frontend                  |
| Pickle           | Model serialization       |

---

## 📂 Project Structure

```text
Forest-Fire-ML-Project/
│
├── app.py
│
├── models/
│   ├── ridge.pkl
│   └── scaler.pkl
│
├── templates/
│   ├── index.html
│   └── home.html
│
├── static/
│   └── ...
│
└── README.md
```

---

## 🧠 Machine Learning Model

The project uses **Ridge Regression**, a regularized version of Linear Regression.

Ridge Regression helps reduce the effect of multicollinearity and prevents the model from relying too heavily on individual features.

The prediction pipeline is:

```text
User Input
    ↓
Feature Extraction
    ↓
StandardScaler
    ↓
Ridge Regression Model
    ↓
Prediction
    ↓
Web Interface
```

---

## 📊 Input Features

The application accepts the following parameters:

| Feature     | Description                 |
| ----------- | --------------------------- |
| Temperature | Temperature value           |
| RH          | Relative Humidity           |
| Ws          | Wind Speed                  |
| Rain        | Rainfall                    |
| FFMC        | Fine Fuel Moisture Code     |
| DMC         | Duff Moisture Code          |
| ISI         | Initial Spread Index        |
| Classes     | Fire classification feature |
| Region      | Region identifier           |

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/Forest-Fire-ML-Project.git
```

Move into the project directory:

```bash
cd Forest-Fire-ML-Project
```

---

### 2. Create a virtual environment

Windows:

```bash
python -m venv .venv
```

Activate it:

```powershell
.venv\Scripts\Activate.ps1
```

If you are using Command Prompt:

```cmd
.venv\Scripts\activate
```

---

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

If you don't have a `requirements.txt` file yet:

```bash
python -m pip install flask numpy pandas scikit-learn
```

---

## ▶️ Run the Application

Start the Flask application:

```bash
python app.py
```

You should see something similar to:

```text
Running on http://127.0.0.1:5000
```

Open your browser and visit:

```text
http://127.0.0.1:5000
```

---

## 🧪 Example Input

You can test the application using sample values such as:

| Parameter   | Example |
| ----------- | ------: |
| Temperature |      38 |
| RH          |      25 |
| Ws          |      20 |
| Rain        |       0 |
| FFMC        |      90 |
| DMC         |      45 |
| ISI         |      12 |
| Classes     |       1 |
| Region      |       1 |

Enter the values into the web form and click the prediction button.

---

## 🔄 How the Application Works

### Step 1 — User Input

The user enters environmental and weather information through the web interface.

### Step 2 — Data Preprocessing

The input data is passed through the saved `StandardScaler`.

```python
new_data_scaled = standard_scaler.transform([
    [Temperature, RH, Ws, Rain, FFMC, DMC, ISI, Classes, Region]
])
```

### Step 3 — Machine Learning Prediction

The scaled data is passed to the trained Ridge Regression model.

```python
result = ridge_model.predict(new_data_scaled)
```

### Step 4 — Display Result

The prediction is returned to the Flask webpage.

---

## 📦 Model Files

The project contains two important serialized Machine Learning files:

### `ridge.pkl`

Contains the trained Ridge Regression model.

### `scaler.pkl`

Contains the StandardScaler used during model training.

Both files are loaded when the Flask application starts.

```python
ridge_model = pickle.load(
    open('models/ridge.pkl', 'rb')
)

standard_scaler = pickle.load(
    open('models/scaler.pkl', 'rb')
)
```

---

## ⚠️ Scikit-learn Version Compatibility

The saved `.pkl` files were originally created using a specific version of scikit-learn.

If you see a warning such as:

```text
InconsistentVersionWarning:
Trying to unpickle estimator Ridge from version 1.2.1
when using version 1.9.1
```

it means the model was trained/saved with an older scikit-learn version.

For long-term compatibility, it is recommended to **retrain and regenerate the `.pkl` files using the scikit-learn version in your current environment**.

Do not simply ignore model compatibility issues when deploying a production application.

---

## 📋 Requirements

Example `requirements.txt`:

```text
Flask
numpy
pandas
scikit-learn
```

You can generate the exact dependencies from your active virtual environment with:

```bash
pip freeze > requirements.txt
```

---

##

---

## 🎯 Learning Outcomes

Through this project, the following concepts are demonstrated:

- Machine Learning model development
- Regression
- Ridge Regression
- Feature scaling
- Data preprocessing
- Model serialization using Pickle
- Flask REST/web application development
- HTML form handling
- Connecting ML models with web applications
- Python virtual environments
- Model deployment concepts

---

## ⚠️ Disclaimer

This project is intended for **educational and demonstration purposes**.

The prediction should not be considered an official forest-fire warning or emergency decision-making system. Real-world fire prediction requires high-quality meteorological, geographical, satellite, vegetation, and historical datasets.

---

## 👨‍💻 Author

**Pranav Gupta**

AI Engineer / GenAi

---

## ⭐ If You Like This Project

If you found this project useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is available for educational and personal use.

