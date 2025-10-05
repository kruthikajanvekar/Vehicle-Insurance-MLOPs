# Vehicle-Insurance-MLOPs

## 🎯 Project Overview
An end-to-end **Vehicle Insurance Cross-Sell Prediction** system using **MLOps best practices**.  
This repository contains an end-to-end MLOps pipeline for a machine learning system built to automate and optimize processes in the vehicle insurance domain.

**Business Goals:**
- Reduce marketing costs  
- Improve conversion rates  
- Enhance customer satisfaction  
- Optimize targeting & resource allocation  

---

## ✨ Features
- **End-to-End ML Pipeline**: From data ingestion → deployment  
- **MLOps Integration**: DVC, MLflow, Docker, CI/CD  
- **FastAPI REST API** for predictions  
- **Monitoring & Retraining** with drift detection  
- **Cloud Ready** AWS
- **Automated Data Validation & Logging**

---

## 🏗️ Architecture
Data Source → Data Ingestion → Validation → Transformation → Model Training → Evaluation → Deployment → FastAPI API

yaml
Copy code

---

## 🛠️ Tech Stack
**Languages:** Python 3.8+  
**Libraries:** scikit-learn, pandas, numpy, FastAPI, Uvicorn  
**MLOps Tools:** MLflow, DVC, Docker, GitHub Actions, pytest  
**Cloud & DB:** AWS S3, EC2, MongoDB/MySQL  

---

**Target:**  
- `Response` → 1 (Interested), 0 (Not Interested)

---

## 🚀 Installation
```bash
# Clone the repo
git clone https://github.com/kruthikajanvekar/Vehicle-Insurance-MLOPs.git
cd Vehicle-Insurance-MLOPs

# Create & activate virtual env
python -m venv venv
venv\Scripts\activate   # (Windows)
source venv/bin/activate # (Linux/Mac)

# Install dependencies
pip install -r requirements.txt
Set environment variables (.env):

env
Copy code
MONGODB_URL=mongodb://localhost:27017/
AWS_ACCESS_KEY_ID=your_access_key
AWS_SECRET_ACCESS_KEY=your_secret_key
S3_BUCKET_NAME=your_bucket_name
MLFLOW_TRACKING_URI=http://localhost:5000
🏃 How to Run
Option 1: Complete Training Pipeline

bash
Copy code
python main.py
Option 2: Start API Server

bash
Copy code
uvicorn app:app --reload --port 8000
# Docs: http://localhost:8000/docs
Option 3: Docker

bash
Copy code
docker build -t vehicle-insurance-mlops .
docker run -p 8000:8000 vehicle-insurance-mlops

📁 Project Structure
bash
Copy code
Vehicle-Insurance-MLOPs/
│
├── src/
│   ├── components/          # Data + Model pipeline modules
│   ├── pipeline/            # Training & prediction scripts
│   ├── utils/               # Helper functions
│   ├── exception.py
│   └── logger.py
│
├── app.py                   # FastAPI application
├── main.py                  # Entry point
├── requirements.txt
├── Dockerfile
└── README.md

🔄 MLOps Pipeline
Data Pipeline → ingestion, validation, transformation

Model Pipeline → training, evaluation, versioning (MLflow)

Deployment → FastAPI REST API, monitoring, retraining

CI/CD → Automated build & test via GitHub Actions

📡 API Endpoints
Method	Endpoint	Description
GET	/	Health Check
POST	/predict	Predict for single input
POST	/predict/batch	Predict for CSV file
GET	/model/info	Get model metadata

Example Request:

json
Copy code
{
  "Gender": "Male",
  "Age": 44,
  "Driving_License": 1,
  "Region_Code": 28.0,
  "Previously_Insured": 0,
  "Vehicle_Age": "1-2 Year",
  "Vehicle_Damage": "Yes",
  "Annual_Premium": 40454.0,
  "Policy_Sales_Channel": 26.0,
  "Vintage": 217
}

📈 Model Performance
Best Model: XGBoost Classifier

Accuracy: 92.3%

Precision: 89.5%

Recall: 91.2%

F1-Score: 90.3%

AUC-ROC: 0.95
