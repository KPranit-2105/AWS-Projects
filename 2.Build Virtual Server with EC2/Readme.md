# Static Web Hosting with Amazon S3

This project demonstrates how to host a static website using Amazon S3. It involves setting up an S3 bucket, configuring it for static website hosting, uploading website files, and testing the deployment.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Prerequisites](#prerequisites)
3. [Step-by-Step Process](#step-by-step-process)
   - [Step 1: Create an S3 Bucket](#step-1-create-an-s3-bucket)
   - [Step 2: Enable Static Website Hosting](#step-2-enable-static-website-hosting)
   - [Step 3: Upload Website Files](#step-3-upload-website-files)
   - [Step 4: Configure Bucket Policy for Public Access](#step-4-configure-bucket-policy-for-public-access)
   - [Step 5: Test Your Static Website](#step-5-test-your-static-website)


---

## Introduction

Amazon S3 (Simple Storage Service) is a highly scalable, cost-effective cloud storage service. This project demonstrates how to leverage S3's capabilities to host static websites, which are ideal for personal portfolios, blogs, or any site with fixed content.

---

## Prerequisites

Before starting, ensure you have:
1. An **AWS account**.
2. Basic understanding of **HTML/CSS/JS** (for creating static website files).
3. AWS CLI (optional, for managing S3 via the command line).

---

## Step-by-Step Process

### Step 1: Create an S3 Bucket
1. Log in to your AWS Management Console.
2. Navigate to the **S3** service.
3. Click **Create Bucket**.
   - Enter a unique bucket name (e.g., `my-static-website-demo`).
   - Choose a region (preferably close to your target audience).
   - Keep the default settings for now and click **Create Bucket**.

---

### Step 2: Enable Static Website Hosting
1. In the S3 dashboard, select your newly created bucket.
2. Go to the **Properties** tab.
3. Scroll down to the **Static website hosting** section and click **Edit**.
4. Enable static website hosting by selecting the option "Enable".
5. Specify the **index document** (e.g., `index.html`) and **error document** (e.g., `error.html`).
6. Save the changes.

---

### Step 3: Upload Website Files
1. Go to the **Objects** tab of your bucket.
2. Click **Upload**.
3. Drag and drop your static website files (e.g., `index.html`, `style.css`, etc.).
4. Click **Upload** to save them to the bucket.

---

### Step 4: Configure Bucket Policy for Public Access
1. Go to the **Permissions** tab of your bucket.
2. Scroll down to the **Bucket policy** section.
3. Click **Edit** and paste the following policy to allow public access to your website:

   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::your-bucket-name/*"
           }
       ]
   }
Replace your-bucket-name with your actual bucket name. 4. Save the changes.

Note: Ensure the Block Public Access settings are properly configured to allow public access.

### Step 5: Test Your Static Website
Go back to the Properties tab.
In the Static website hosting section, note the Endpoint URL.
Open the endpoint URL in your browser to view your static website.

Author
Pranit P. Kolamkar
