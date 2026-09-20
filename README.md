# Data Science & Machine Learning Internship Portfolio

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E.svg?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg?logo=tensorflow)](https://www.tensorflow.org/)
[![Flask](https://img.shields.io/badge/Flask-Web%20API-lightgrey.svg?logo=flask)](https://flask.palletsprojects.com/)
[![PuLP](https://img.shields.io/badge/PuLP-Linear%20Programming-brightgreen.svg)](https://coin-or.github.io/pulp/)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

A comprehensive collection of practical Data Science, Deep Learning, and Operations Research projects completed during the Data Science internship. 

This repository covers end-to-end industry workflows across data engineering pipelines, computer vision deep neural networks, machine learning model deployment via REST APIs, and mathematical business optimization.

---

## 📌 Projects Overview

| Task | Domain | Core Tech Stack | Description | Status |
|---|---|---|---|---|
| **[Task 1](#-task-1-automated-etl--data-pipeline-development)** | Data Engineering & Preprocessing | `Pandas`, `NumPy`, `Scikit-Learn` | End-to-end automated ETL pipeline handling missing data imputation, standard scaling, and one-hot encoding. | `Completed` ✅ |
| **[Task 2](#-task-2-deep-learning-image-classification-cifar-10)** | Computer Vision / Deep Learning | `TensorFlow`, `Keras`, `Matplotlib` | Multi-class image classification using a Convolutional Neural Network (CNN) trained on the CIFAR-10 dataset. | `Completed` ✅ |
| **[Task 3](#-task-3-machine-learning-api-deployment)** | ML Model Deployment | `Flask`, `scikit-learn`, `pyngrok` | Advertising budget sales prediction model deployed as a cloud-accessible REST API with public ngrok tunneling. | `Completed` ✅ |
| **[Task 4](#-task-4-operations-research--linear-programming-optimization)** | Prescriptive Analytics / Optimization | `PuLP`, `Optimization Theory` | Business profit maximization under resource and labor constraints using Linear Programming (Simplex method). | `Completed` ✅ |

---

## 🛠️ Task Details & Implementation

### 🔹 Task 1: Automated ETL & Data Pipeline Development
* **Objective**: Build a robust, production-ready data pipeline to transform raw, messy tabular data into clean, normalized feature matrices for machine learning models.
* **Pipeline Architecture**:
  * **Extraction**: Reads raw structured tabular files (`raw_data.csv`).
  * **Imputation**: Handles missing values via `SimpleImputer` (median strategy for numerical features, most frequent for categorical).
  * **Feature Scaling**: Applies `StandardScaler` to bring numeric fields (`age`, `income`) to zero mean and unit variance.
  * **Encoding**: Uses `OneHotEncoder` on categorical fields (`city`) with `drop="first"` to eliminate multicollinearity.
  * **Loading**: Exports normalized feature matrix and target vectors to `processed_data.csv`.
* **Execution**:
  ```bash
  python task1
  ```

---

### 🔹 Task 2: Deep Learning Image Classification (CIFAR-10)
* **Objective**: Design, train, and evaluate a Convolutional Neural Network (CNN) to classify 32x32 color images across 10 object categories (airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck).
* **Architecture**:
  * Convolutional layer 1 (32 filters, 3x3 kernel, ReLU) + MaxPooling2D (2x2)
  * Convolutional layer 2 (64 filters, 3x3 kernel, ReLU) + MaxPooling2D (2x2)
  * Convolutional layer 3 (64 filters, 3x3 kernel, ReLU)
  * Dense classification head (64 hidden units) + Softmax output (10 classes)
* **Performance**: Achieves high validation accuracy with epoch-by-epoch learning curve visualization using Matplotlib.
* **Notebook**: Open and execute [`task2.ipynb`](task2.ipynb) directly in Google Colab.

---

### 🔹 Task 3: Machine Learning API Deployment
* **Objective**: Train a multivariate regression model on advertising expenditures (TV, Radio, Newspaper) to forecast product sales, and deploy it as a production RESTful microservice.
* **Key Components**:
  * **Model Training**: Linear Regression with train/test validation split, serialized with `pickle` into `model.pkl`.
  * **Flask REST API**: Endpoints for root health check (`/`) and batch prediction requests (`/predict`).
  * **Cloud Tunneling**: Integrated with `pyngrok` for secure, public web tunneling to consume the API from any remote application or web frontend.
* **API Payload Example**:
  ```json
  POST /predict
  Content-Type: application/json

  {
    "TV": 150.0,
    "Radio": 25.0,
    "Newspaper": 10.0
  }
  ```
  **Response**:
  ```json
  {
    "status": "success",
    "predicted_sales": 13.52
  }
  ```
* **Notebook**: [`task3.ipynb`](task3.ipynb)

---

### 🔹 Task 4: Operations Research & Linear Programming Optimization
* **Objective**: Formulate and solve an optimal production planning model using mathematical optimization to maximize business profit under operational constraints.
* **Mathematical Formulation**:
  * **Objective Function**:
    $$\text{Maximize } Z = 40A + 30B$$
  * **Subject to Constraints**:
    * Labor constraint: $2A + B \le 100$ hours
    * Raw Material constraint: $A + B \le 40$ units
    * Non-negativity & Integer constraints: $A, B \ge 0 \quad (A, B \in \mathbb{Z})$
* **Optimal Solution Discovered**:
  * **Product A**: 40 units
  * **Product B**: 0 units
  * **Maximum Profit**: **$1,600.00**
* **Notebook**: [`task4.ipynb`](task4.ipynb)

---

## 📂 Repository Structure

```
data-science/
├── task1                      # Automated ETL & Scikit-Learn pipeline script
├── task2.ipynb                # CIFAR-10 CNN Image Classification Notebook
├── task3.ipynb                # Sales Prediction ML Model & Flask REST API
├── task4.ipynb                # Linear Programming Profit Optimization
├── raw_data.csv               # Raw sample dataset with missing values & categories
├── processed_data.csv         # Cleaned, imputed, and scaled output dataset
└── README.md                  # Detailed portfolio documentation
```

---

## 🚀 Getting Started Locally

### 1. Clone the Repository
```bash
git clone https://github.com/KHAGESH-46/data-science.git
cd data-science
```

### 2. Set Up Virtual Environment & Install Dependencies
```bash
python -m venv .venv

# On Windows:
.venv\Scripts\activate
# On Linux / macOS:
source .venv/bin/activate

# Install required packages:
pip install pandas numpy scikit-learn tensorflow matplotlib flask pyngrok pulp
```

### 3. Run Any Project
```bash
# Run Task 1 data pipeline:
python task1

# Launch Jupyter to explore notebooks:
jupyter notebook
```

---

## 👤 Author

* **Khagesh Attarde**
* GitHub: [@KHAGESH-46](https://github.com/KHAGESH-46)
* Email: [kpattarde22@gmail.com](mailto:kpattarde22@gmail.com)
