# End-to-End Machine Learning Project

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=for-the-badge&logo=mysql&logoColor=white)
![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![MLflow](https://img.shields.io/badge/mlflow-%23d9ead3.svg?style=for-the-badge&logo=mlflow&logoColor=blue)

## 📌 Detailed Overview

This project serves as a comprehensive, production-grade template for building **End-to-End Machine Learning Pipelines**. In the rapidly evolving field of data science, moving from a Jupyter Notebook to a deployable application is a critical skill. This repository demonstrates exactly how to bridge that gap.

The core objective is to create a robust system that handles the complete data lifecycle:
1.  **Data Ingestion**: Systematically extracting data from various sources (specifically MySQL databases in this implementation), handling splitting, and raw data storage.
2.  **Data Transformation**: Implementing reproducible and thoroughly tested preprocessing pipelines. This includes handling missing values, encoding categorical variables, and scaling features, ensuring that the exact same transformations applied during training are applied during inference.
3.  **Model Training & Selection**: Beyond simple model fitting, this project employs advanced ensemble techniques like **CatBoost** and **XGBoost** alongside traditional regressors. It systematically evaluates models to select the best performer based on metrics like R2 Score.
4.  **Experiment Tracking**: Integrated with **MLflow**, every run is logged. You can track hyperparameters, metrics, and serialized models, making the experimentation process transparent and reproducible.
5.  **Deployment Ready**: The project is structured with `app.py` as an entry point and includes `Dockerfile` support, making it ready for containerization and deployment to cloud platforms like AWS EC2, Azure, or Google Cloud Run.

This architecture ensures that the machine learning solution is not just a "model file" but a complete, maintainable software product.

## ✨ Key Features

- **🏭 Modular Codebase**: Written with software engineering best practices. each step (ingestion, transformation, training) is its own component `src/mlproject/components`, making it easy to debug and extend.
- **🔄 Automatation Pipelines**: 
    - **Training Pipeline**: Automates the flow from raw data to a saved model.
    - **Prediction Pipeline**: tailored for real-time or batch inference using the saved artifacts.
- **🚀 Advanced Algorithms**: Leverages the power of Gradient Boosting libraries (**CatBoost**, **XGBoost**) for superior performance on tabular data.
- **📊 MLflow Integration**: First-class support for MLOps. Track experiments, compare runs, and manage model versions effortlessly.
- **🛡️ Robust Error Handling**: Custom `Exception` handling and uniform `Logging` ensure that any issue in the pipeline is traceable and easy to fix.
- **🐳 Dockerized**: Includes a `Dockerfile` for creating lightweight, portable containers of the application.

## 🛠️ Technologies Used

| Category | Tools |
|----------|-------|
| **Languages** | ![Python](https://img.shields.io/badge/python-3670A0?style=flat-square&logo=python&logoColor=ffdd54) |
| **Data Processing** | ![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat-square&logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=flat-square&logo=numpy&logoColor=white) |
| **Machine Learning** | ![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=flat-square&logo=scikit-learn&logoColor=white) ![XGBoost](https://img.shields.io/badge/XGBoost-%23150458.svg?style=flat-square&logo=xgboost&logoColor=white) ![CatBoost](https://img.shields.io/badge/CatBoost-green?style=flat-square) |
| **Database** | ![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=flat-square&logo=mysql&logoColor=white) |
| **MLOps** | ![MLflow](https://img.shields.io/badge/mlflow-%23d9ead3.svg?style=flat-square&logo=mlflow&logoColor=blue) |
| **DevOps** | ![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat-square&logo=docker&logoColor=white) |

## 📂 Project Structure
```
mlprojecthindi-main/
├── artifacts/             # Stores train/test data, models, and preprocessors
├── catboost_info/         # CatBoost training logs
├── mlruns/                # MLflow tracking data
├── src/
│   └── mlproject/
│       ├── components/    # Core logic modules (Ingestion, Transformation, Training)
│       ├── pipelines/     # Training and Prediction workflows
│       ├── exception.py   # Custom exception handling
│       ├── logger.py      # Logging configuration
│       └── utils.py       # Utility functions
├── app.py                 # Main execution script for the pipeline
├── main.py                # Setup script
├── requirements.txt       # Python dependencies
├── Dockerfile             # Container configuration
└── README.md              # Project documentation
```

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- MySQL Server (for data source)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Arnab-Ghosh7/Model-to-Production-ML
   cd mlprojecthindi-main
   ```

2. **Create a Virtual Environment** (Recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

### Configuration
- Ensure you have a `.env` file or environment variables set up for your MySQL database connection logic (host, user, password, db).

## 🏃 Usage

To run the full training pipeline (Ingestion -> Transformation -> Training):

```bash
python app.py
```

Arguments and configurations can be adjusted within the `app.py` or the specific component configuration classes in `src/mlproject/config`.

## 📈 Experiment Tracking
MLflow is initialized to track your experiments. To view the dashboard:
```bash
mlflow ui
```

## 🤝 Contributing
Contributions are welcome! Please fork the repository and submit a Pull Request.

## 📝 License
This project is open-source.
