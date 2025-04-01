# Customer Churn Prediction & Email Automation System

## **Project Overview**
This project predicts customer churn using machine learning and automates personalized email outreach for customers at risk of leaving. It uses a variety of machine learning models, including **Logistic Regression**, **Random Forest**, **XGBoost**, **Artificial Neural Networks (ANN)**, and **Auto-Sklearn** to identify at-risk customers and automatically send retention emails.

## **Table of Contents**
1. [Installation](#installation)
2. [Technologies Used](#technologies-used)
3. [Project Features](#project-features)
4. [How to Run](#how-to-run)
5. [API Endpoints](#api-endpoints)
6. [SRS Document](#srs-document)
7. [Model Evaluation](#model-evaluation)
8. [License](#license)
9. [Future Enhancements](#future-enhancements)

## **Installation**

### Prerequisites
Make sure you have the following installed:
- Python 3.x
- pip (Python package manager)

### Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/AmrithNiyogi/Customer-Churn-Prediction.git
   cd Customer-Churn-Prediction
   ```

2. Create and activate a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
---

## **Technologies Used**
- **Programming Language:** Python
- **Libraries & Frameworks:** 
  - Scikit-Learn, XGBoost, TensorFlow/Keras, Auto-Sklearn
  - Flask for API development
  - smtplib, imaplib for email automation
  - Pandas for data manipulation
- **Database:** Pandas DataFrame (extendable to SQL/NoSQL if needed)
- **Model Deployment:** Joblib for model persistence

## **Project Features**
- **Customer Churn Prediction**: Predicts whether a customer will churn using machine learning models.
- **Email Automation**: Sends personalized retention emails to at-risk customers.
- **API Integration**: Flask API to deploy the churn prediction model and email automation system.

---

## **How to Run**

### Run the Flask API Locally
1. Start the Flask development server:
   ```bash
   python app.py
   ```
   This will run the API locally at `http://127.0.0.1:5000/`.

2. The API can be tested by sending POST requests to the following endpoints:
   - `/predict`: For churn prediction.
   - `/send-email`: To send a retention email.
   - `/email-status`: To check email engagement.

### Example Request to Predict Churn
```bash
curl -X POST -H "Content-Type: application/json" -d '{"customer_data": {"age": 35, "account_length": 5, "contract_type": "monthly"}}' http://127.0.0.1:5000/predict
```

### Example Request to Send Retention Email
```bash
curl -X POST -H "Content-Type: application/json" -d '{"email": "customer@example.com"}' http://127.0.0.1:5000/send-email
```
---

## **SRS Document**
For detailed project requirements and specifications, you can refer to the [Software Requirements Specification (SRS) document](https://github.com/AmrithNiyogi/Customer-Churn-Prediction/blob/main/SRS/Software%20Requirement%20Specification.md).

---

## **API Endpoints**

### **POST /predict**
- **Description**: Accepts customer data as input and returns churn prediction.
- **Input**: JSON object containing customer features.
- **Output**: JSON object with churn prediction (1 = churn, 0 = not churn).

### **POST /send-email**
- **Description**: Sends a personalized email to a customer identified as at risk of churning.
- **Input**: Customer email address.
- **Output**: Success message or error message.

### **GET /email-status**
- **Description**: Retrieves the email engagement metrics (opened, clicked, etc.).
- **Output**: JSON object with email interaction data.

---

## **Model Evaluation**

The following models were evaluated for churn prediction:
- **Logistic Regression**
- **Random Forest Classifier**
- **XGBoost**
- **Artificial Neural Network (ANN)**
- **Auto-Sklearn**

The **best-performing model** based on metrics such as **accuracy**, **precision**, **recall**, **F1-score**, and **ROC-AUC** was selected for deployment.

---

## **License**
This project is licensed under the **Apache 2.0 License** - see the [LICENSE](LICENSE) file for details.

---

## **Future Enhancements**
- Integrate the system with CRM platforms for dynamic customer data management.
- Implement multi-channel customer outreach (SMS, WhatsApp, etc.).
- Experiment with deep learning models to further improve churn prediction accuracy.
- Add functionality to support batch email sending for large datasets.
