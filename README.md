# Credit Score Classification App

## ❓**What is it?**

A web application for credit score classification using machine learning, built using **Streamlit** (front-end) connected to an **AWS SageMaker** Endpoint (back-end). 
Users can enter financial, credit history, and personal profile of clients. Then, the input data is sent as a JSON payload to a deployed SageMaker endpoint. Finally, it returns a predicted credit score classification: Good/Standard/Bad.

The **main features** include:

* Input form built using Streamlit
* Uses financial, credit history, and profile information to make a credit score prediction
* Sends prediction requests to an AWS SageMaker Endpoint*
* Predicts a credit score class:
  * 🟢 **Good**
  * 🟡 **Standard**
  * 🔴 **Bad**

## 🌱 Project Structure

```text
├── streamapp.py
└── requirements.txt
```

### `streamapp.py`

Contains the main Streamlit application that:

* Creates the user input interface
* Processes the prediction payload
* Connects to the AWS SageMaker Runtime API using boto3
* Invokes the deployed SageMaker endpoint
* Displays the prediction result

### `requirements.txt`

Contains the Python dependencies required to run the Streamlit application.

## Requirements

* Python 3.9+
* An active AWS account
* A deployed **Amazon SageMaker inference endpoint**
* AWS credentials with permission to invoke the SageMaker endpoint

## ☁️ AWS Configuration

The application uses boto3 to communicate with the SageMaker Runtime API. If you want to customize it (i.e. changing the endpoint/ML model), change the following environment variables:

```bash
ENDPOINT_NAME=credit-score-123
AWS_REGION=us-east-1
```

Make sure the AWS credentials are configured and have permission to invoke the SageMaker endpoint.

## 🏃 How to run it?

Start the Streamlit application with:

```bash
streamlit run streamapp.py
```
The application should open automatically in your default browser.

If it does not open automatically, copy the Local URL generated in the terminal, like:

http://localhost:8501

## 🛠️ How it works?
This diagram should briefly explain the workflow:

```text
User Input
    │
    ▼
Streamlit Application
    │ JSON Payload
    ▼
AWS SageMaker Runtime
    │
    ▼
SageMaker Endpoint
    │ Prediction Response
    ▼
Streamlit Application
    │
    ▼
Credit Score Result & Interpretation
```

The endpoint is expected to return a response containing predictions.

## ⌨️ Tech Stack

* **Python**
* **Streamlit** — Web application interface
* **Boto3** — AWS SDK for Python
* **Amazon SageMaker** — Model hosting and inference

## Notes 
This repository contains the Streamlit frontend only.
The machine learning model and its SageMaker deployment are hosted separately on AWS. Also, my SageMaker endpoint might be disabled if all allocated AWS credits have been spent.
