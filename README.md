#  🖥️ AWS Lambda JSON Response API

![AWS](https://img.shields.io/badge/Built%20with-AWS-orange?style=flat&logo=amazonaws)
![Project Status](https://img.shields.io/badge/status-finished-green)

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

python

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
## Step 1: Create the Lambda Function (via AWS Console)
#### 🔹 Go to: AWS Lambda Console

![image alt](https://github.com/Juniorklb/Lambda-function-returning-JSON/blob/8592a91963e0de9e7d1b56add8fb39ddeed6c2dd/Images/lambdacreation.PNG)
- Click **"Create function"**
  
- Function name: jsonResponseHandler

- Runtime: Python 3.12 (or latest available)

- Choose "Author from scratch"

- Leave permissions as default (you can create a new role with basic Lambda permissions)

- Click **"Create function"**

####  ✍️ Paste This Code in the Function Editor:

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
- Click “Deploy” to save the changes.
- Your Lambda function is now ready!
  
## Step 2: Create an API Gateway (HTTP API)

- Go to: API Gateway Console
- Choose “HTTP API” (not REST)
- Click “Build” under HTTP API

#### 🧾 Step-by-Step:
- Choose **“Add Integration”**

- Select Lambda

- Pick your Lambda function: ``jsonResponseHandler``
  
    - Configure Route

    - Method: GET

- Resource path: /hello (or anything you prefer)

    - Configure Stage

- Name: dev (or any environment name)

   - Leave defaults

   - Review & Create

   - Review all settings

    - Click Create

#### Once created:
- You’ll see your API invoke URL, something like:

``https://abcd1234.execute-api.us-east-1.amazonaws.com/hello``
#### 🧪 Test It

**💻 Terminal:**

``curl https://abcd1234.execute-api.us-east-1.amazonaws.com/hello``

**Browser or Postman:**

- Just paste the URL in the browser.

- You should receive a JSON response like:

      {
      "message": "Hello from Lambda!",
      "status": "success"
      }
## Project Conclusion: AWS Lambda JSON Response API

- You’ve successfully:

- Created a serverless AWS Lambda function using Python

- Integrated it with API Gateway to expose it as a public HTTP endpoint

- Extended it to handle query parameters (e.g., ?name=John)

- Built a lightweight, dynamic JSON API

- Prepared a professional GitHub README for documentation
## 📚 Author
![AWS](https://img.shields.io/badge/Built%20with-AWS-orange?style=flat&logo=amazonaws) by Junior Kalomba
**🔗 Feel free to contribute or suggest improvements!** 
<p align="right">
  <a href="https://www.linkedin.com/in/junior-kalomba-10002a18a/" target="_blank">
    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="junior-kalomba-10002a18a" height="30" width="40"/>  
