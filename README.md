# # 🖥️ AWS Lambda JSON Response API

### ☁️ Built with Amazon Web Services (AWS)

![AWS](https://img.shields.io/badge/Built%20with-AWS-orange?style=flat&logo=amazonaws)
![Project Status](https://img.shields.io/badge/status-in--progress-yellow)

This project demonstrates how to create a simple AWS Lambda function that returns a JSON response when triggered through an API Gateway. It's a lightweight serverless API ideal for learning, testing, or serving small microservices.

---

## 🚀 Technologies Used

- **AWS Lambda** (Python 3.x)
- **Amazon API Gateway (HTTP API)**
- **AWS IAM**
- **CloudWatch Logs**

---

## 📦 Features

- Simple HTTP GET API
- JSON response returned from Lambda
- Serverless architecture
- Easily extendable to accept query parameters or POST data

---

## 🛠️ Setup Instructions

### 1. Create the Lambda Function
- Go to AWS Lambda Console
- Create a new function using Python
- Paste the following code:

```python
import json

def lambda_handler(event, context):
    print("Received event:", json.dumps(event))
    return {
        'statusCode': 200,
        'body': json.dumps({
            'message': 'Hello from Lambda!',
            'status': 'success'
        }),
        'headers': {
            'Content-Type': 'application/json'
        }
    }
