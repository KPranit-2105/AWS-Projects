# Deploy a Scalable Web App using Elastic Beanstalk

## Overview
This project demonstrates how to deploy a scalable web application using AWS Elastic Beanstalk. The application is designed to handle variable workloads by leveraging AWS's auto-scaling capabilities.

## Features
- **Scalability**: Automatically adjusts capacity based on traffic demand.
- **Managed Deployment**: Simplifies application management using AWS Elastic Beanstalk.
- **Load Balancing**: Ensures high availability and fault tolerance.
- **Logging & Monitoring**: Uses AWS CloudWatch for monitoring and logging.
- **Database Integration**: Connects to Amazon RDS for persistent data storage.

## Prerequisites
Before deploying the application, ensure you have the following:
- An AWS account
- AWS CLI installed and configured
- Elastic Beanstalk CLI installed
- A web application (Node.js, Python, Java, etc.)

## Project Setup
### 1. Clone the Repository
```bash
git clone <repository-url>
cd <project-directory>
```

### 2. Initialize Elastic Beanstalk
```bash
eb init
```
Follow the prompts to configure your application and select the appropriate AWS region.

### 3. Deploy the Application
```bash
eb create <environment-name>
```
This command will create a new environment and deploy your application.

### 4. Check Deployment Status
```bash
eb status
eb health
```

### 5. Updating the Application
After making changes to your code, redeploy using:
```bash
eb deploy
```

## Environment Configuration
Modify `config.yml` or environment variables as needed to customize settings such as:
- **Instance type**
- **Auto-scaling policies**
- **Database connection details**

## Monitoring & Logging
Use AWS CloudWatch for monitoring:
```bash
eb logs
```
Check performance metrics in the AWS Management Console under **Elastic Beanstalk > Monitoring**.

## Cleaning Up Resources
To terminate the environment and prevent unnecessary costs:
```bash
eb terminate <environment-name>
```

## Technologies Used
- **AWS Elastic Beanstalk** for deployment
- **Amazon RDS** for database management
- **Amazon S3** for static file storage (optional)
- **CloudWatch** for monitoring and logging

## License
This project is licensed under the MIT License. Feel free to modify and distribute it as needed.

## Author
Pranit P. Kolamkar
