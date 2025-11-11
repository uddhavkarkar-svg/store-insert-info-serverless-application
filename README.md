# store-insert-info-serverless-application

# Serverless Web Application on AWS

This project demonstrates how to deploy a **serverless web application** on AWS by integrating multiple AWS services. The architecture leverages **S3, API Gateway, Lambda, DynamoDB, and CloudFront** to deliver a secure, scalable, and cost-effective application.

---

## Architecture Overview

- **Amazon S3** → Hosts static web content (HTML, CSS, JavaScript).
- **Amazon API Gateway** → Provides REST API endpoints for client-server communication.
- **AWS Lambda** → Handles business logic for GET and POST requests.
- **Amazon DynamoDB** → NoSQL database for storing and retrieving data.
- **Amazon CloudFront** → Secures and accelerates delivery of web content via HTTPS.

---

## Steps to Deploy

### 1. Setting up an S3 Bucket
- Create an S3 bucket to host your static website.
- Upload `index.html`, `style.css`, and JavaScript files.
- Enable **Static Website Hosting** in S3.
- Configure bucket policy for public read access (if required).
- ![Alt text](C:\uddhav workpress\project\store-insert-info-serverless-application\project\Screenshot (11).png)


### 2. Configuring API Gateway
- Create a **REST API** in API Gateway.
- Define endpoints (e.g., `/items`).
- Set up methods:
  - **GET** → Fetch data from DynamoDB.
  - **POST** → Insert new data into DynamoDB.
- Integrate each method with its corresponding Lambda function.
- ![Alt text](C:\uddhav workpress\project\store-insert-info-serverless-application\project\Screenshot (7).png)


### 3. Creating Lambda Functions
- Write Lambda functions in **Python** (or Node.js) to handle API Gateway requests.
- Example functions:
  - `get_item` → Retrieve data from DynamoDB.
  - `create_item` → Insert new records into DynamoDB.
- Grant Lambda functions appropriate **IAM roles** to access DynamoDB.
- ![Alt text](C:\uddhav workpress\project\store-insert-info-serverless-application\project\Screenshot (6).png)


### 4. Working with DynamoDB
- Create a DynamoDB table with a suitable **primary key**.
- Use Lambda to perform **CRUD operations**:
  - Create
  - Read
  - Update
  - Delete
- Ensure proper read/write capacity (On-demand or Provisioned).
- ![Alt text](C:\uddhav workpress\project\store-insert-info-serverless-application\project\Screenshot (5).png)


### 5. Implementing Secure Connections with CloudFront
- Create a **CloudFront Distribution** pointing to your S3 bucket.
- Enable **HTTPS** with an SSL certificate from **AWS Certificate Manager (ACM)**.
- Configure caching policies for performance optimization.
- Restrict direct S3 access using **Origin Access Control (OAC)**.
- ![Alt text](C:\uddhav workpress\project\store-insert-info-serverless-application\project\Screenshot (12).png)


---

## Benefits of this Architecture
- **Serverless**: Pay only for what you use, no server management.
- **Scalable**: Handles sudden traffic spikes automatically.
- **Secure**: HTTPS with CloudFront + IAM policies.
- **Global Performance**: Faster delivery with CloudFront CDN.
- **Cost-Effective**: Uses AWS free tier and pay-as-you-go services.

---

## Next Steps
- Add authentication with **Amazon Cognito**.
- Automate deployment with **AWS SAM or CDK**.
- Monitor application with **CloudWatch**.

---

