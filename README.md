# RSVP Application on AWS

This is a simple **RSVP application** built with an **AWS Lambda backend**, **DynamoDB**, and **Amplify for the frontend**. The backend allows users to submit RSVPs and view existing responses. The application is fully integrated with AWS services, using API Gateway for HTTP APIs, DynamoDB for data storage, and Lambda for backend processing.

## Project Structure

/rsvp-app

index.html # Frontend HTML file

README.md # This readme file


---

## Prerequisites

Before setting up this project, ensure you have the following:

- **AWS Account** (with IAM access)
- **Amplify Console** for hosting the frontend
- **AWS CLI** for deploying resources, if necessary

---

## Step-by-Step Deployment

### 1) **Create DynamoDB Table**

- **Table Name:** `RSVPs`
- **Partition Key:** `eventId` (Type: String)
- **Sort Key:** `createdAt` (Type: Number)
- **Capacity Mode:** On-demand (or provisioned if you know how)

### 2) **Create Lambda Function**

1. Go to the **AWS Lambda Console** → Create a new function:  
   
2. Attach AWS SDK Layer

3. **Set Environment Variables for Lambda**
   - TABLE_NAME = RSVPs

4. **Attach IAM Role with Permissions**
   - Attach an inline policy with the following content to allow `PutItem` and `Query` operations for your DynamoDB table (`RSVPs`):
