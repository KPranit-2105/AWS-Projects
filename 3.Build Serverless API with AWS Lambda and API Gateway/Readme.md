# Build a Serverless API with AWS Lambda and API Gateway

This project demonstrates how to build a serverless RESTful API using AWS Lambda and API Gateway. It leverages AWS services to create scalable and cost-efficient APIs without the need to manage infrastructure.

---

## Table of Contents

1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Step-by-Step Process](#step-by-step-process)
   - [Step 1: Create a Lambda Function](#step-1-create-a-lambda-function)
   - [Step 2: Configure API Gateway](#step-2-configure-api-gateway)
   - [Step 3: Link API Gateway to Lambda](#step-3-link-api-gateway-to-lambda)
   - [Step 4: Deploy the API](#step-4-deploy-the-api)
   - [Step 5: Test Your API](#step-5-test-your-api)
4. [Key Learnings](#key-learnings)
5. [Conclusion](#conclusion)

---

## Introduction

AWS Lambda and API Gateway together provide a fully managed platform for building serverless APIs. With Lambda, you can write and deploy code without worrying about the underlying infrastructure, and API Gateway enables you to expose those Lambda functions as RESTful APIs.

---

## Prerequisites

Before you begin, ensure you have:
- An **AWS account**.
- Familiarity with **Node.js, Python**, or another supported programming language for writing Lambda functions.
- AWS CLI (optional, for managing resources via the command line).

---

## Step-by-Step Process

### Step 1: Create a Lambda Function

1. Log in to the **AWS Management Console**.
2. Navigate to the **Lambda** service and click **Create function**.
3. Choose **Author from scratch**:
   - Function name: `MyServerlessAPI`
   - Runtime: Select a runtime (e.g., Node.js 18.x or Python 3.x).
4. Click **Create function**.
5. Write the Lambda function logic:
   - Example (Node.js):
     ```javascript
     exports.handler = async (event) => {
         const response = {
             statusCode: 200,
             body: JSON.stringify({ message: "Hello from Lambda!" }),
         };
         return response;
     };
     ```
6. Click **Deploy** to save your function.

---

### Step 2: Configure API Gateway

1. Navigate to the **API Gateway** service and click **Create API**.
2. Choose **HTTP API** for a simple and cost-efficient setup.
3. Click **Build**.
4. Specify an API name (e.g., `MyServerlessAPI`) and click **Next**.
5. Click **Add integration** and choose **Lambda Function**.
6. Select your Lambda function from the list and click **Create**.

---

### Step 3: Link API Gateway to Lambda

1. In the API Gateway console, configure routes:
   - Click **Add route**.
   - Select an HTTP method (e.g., `GET`) and specify the path (e.g., `/hello`).
   - Link this route to the Lambda function integration created earlier.
2. Save the route.

---

### Step 4: Deploy the API

1. Navigate to the **Deployments** section in API Gateway.
2. Click **Create deployment**.
3. Specify a stage name (e.g., `prod`) and deploy the API.
4. Note the **Endpoint URL** provided by API Gateway (e.g., `https://<api-id>.execute-api.<region>.amazonaws.com/prod/hello`).

---

### Step 5: Test Your API

1. Use the **Endpoint URL** to test your API:
   - Open a browser or use tools like Postman or cURL.
   - For example, if your URL is `https://abc123.execute-api.us-east-1.amazonaws.com/prod/hello`, send a `GET` request to it.
2. Verify the response from your Lambda function (e.g., `{ "message": "Hello from Lambda!" }`).

---

## Key Learnings

This project helped demonstrate:
- The power of serverless architecture for building scalable APIs.
- How to use AWS Lambda to execute backend logic without managing servers.
- How to use API Gateway to expose Lambda functions as RESTful endpoints.
- The seamless integration between AWS services for rapid API development.

---

## Conclusion

Building a serverless API with AWS Lambda and API Gateway is a great way to create highly scalable and cost-efficient applications. By following this guide, you now have the knowledge to deploy your own serverless APIs in the AWS cloud.

If you have any questions or suggestions, feel free to reach out!

---

### Author
Pranit P. Kolamkar  

