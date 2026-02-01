# Wine Quality Prediction 🍷

[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3100/)
[![DVC](https://img.shields.io/badge/Data%20Version%20Control-DVC-9cf)](https://dvc.org/)
[![MLflow](https://img.shields.io/badge/MLflow-Tracking-blue)](https://mlflow.org/)
[![Dagshub](https://img.shields.io/badge/Dagshub-Experiment%20Tracking-black)](https://dagshub.com/)
[![CI Pipeline](https://github.com/punityadav2/wine_quality_prediction/actions/workflows/ci-only.yaml/badge.svg)](https://github.com/punityadav2/wine_quality_prediction/actions)

End-to-end Machine Learning pipeline for predicting wine quality. This project demonstrates MLOps best practices including modular coding, DVC for data versioning, MLflow (via Dagshub) for experiment tracking, and CI/CD with GitHub Actions.

---

## 🚀 Key Features

*   **Modular Pipeline**: Split into Data Ingestion, Validation, Transformation, Training, and Evaluation.
*   **Data Version Control (DVC)**: Large datasets are tracked via DVC (Local storage configured).
*   **Experiment Tracking**: MLflow integrated with Dagshub for logging metrics, parameters, and models.
*   **CI/CD**: Automated testing pipeline using GitHub Actions.
*   **API**: Flask-based web application for real-time predictions.
*   **Containerization**: Docker support for reproducible deployment.

---

## 🛠️ Setup & Installation

### 1. Clone & Environment
```bash
git clone https://github.com/punityadav2/wine_quality_prediction.git
cd wine_quality_prediction

# Create Virtual Environment
python -m venv venv
.\venv\Scripts\Activate.ps1   # PowerShell
# source venv/bin/activate    # Linux/Mac
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Pull Data (DVC)
Since the data is versioned with DVC, you need to pull it to your local machine:
```bash
dvc pull
```

### 4. Configure Experiment Tracking (Dagshub)
Create a `.env` file in the root directory:
```bash
# .env file content
MLFLOW_TRACKING_URI=https://dagshub.com/YOUR_USERNAME/wine_quality_prediction.mlflow
MLFLOW_TRACKING_USERNAME=YOUR_USERNAME
MLFLOW_TRACKING_PASSWORD=YOUR_DAGSHUB_TOKEN
```

---

## 🏃‍♂️ Usage

### Run the ML Pipeline
To execute the full training pipeline (Ingestion -> Evaluation):
```bash
python main.py
```

### Run the Web App
To start the Flask API and UI:
```bash
python app.py
```
Access the app at `http://localhost:8080`

---

## 🏗️ Project Structure

```
├── .github/workflows  # CI/CD Workflows
├── .dvc/              # DVC Configuration
├── artifacts/         # DVC tracked files (Data, Models) - Ignored by Git
├── config/            # Configuration files
├── src/               # Source code modules
├── templates/         # HTML templates for Flask
├── app.py             # Flask Application
├── main.py            # Main training pipeline entry point
├── dvc.yaml           # DVC pipeline definition
└── params.yaml        # Training parameters
```

---

## ☁️ Deployment

The project includes a `Dockerfile` and is ready for deployment on platforms like AWS EC2, Azure, or Render. A dedicated AWS deployment workflow is available in `.github/workflows/main.yaml.disabled`.
