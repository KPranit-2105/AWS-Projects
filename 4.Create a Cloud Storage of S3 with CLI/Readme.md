# Cloud Storage in S3 Using AWS CLI

This project demonstrates how to create and manage cloud storage in Amazon S3 using the AWS Command Line Interface (CLI). By following the steps outlined in this guide, you will be able to create an S3 bucket, upload a file, list the contents of the bucket, and generate a pre-signed URL for file access.

---

## Prerequisites

Before starting, ensure you have the following:

- An AWS account
- AWS CLI installed and configured with valid IAM credentials (`aws configure`)
- A stable internet connection

---

## Step 1: Create an S3 Bucket
To create an S3 bucket, use the `aws s3 mb` command. The bucket name must be unique across all AWS accounts:

aws s3 mb s3://your-bucket-name

## Step 2: Upload a File to the Bucket
Use the aws s3 cp command to upload a file to the newly created bucket:

aws s3 cp your-file.txt s3://your-bucket-name/

## Step 3: List Files in the S3 Bucket
To verify that the file was uploaded successfully, list the contents of the bucket using:

aws s3 ls s3://your-bucket-name/

## Step 4: Generate a Pre-Signed URL
A pre-signed URL allows temporary access to a file stored in S3 without requiring AWS credentials. Generate a URL for your uploaded file using:

aws s3 presign s3://your-bucket-name/your-file.txt



 ## Conclusion
By following these steps, you have successfully:

Created an S3 bucket
Uploaded a file using AWS CLI
Listed the files in the bucket
Generated a pre-signed URL for secure file sharing
This mini-project provides a foundational understanding of AWS S3 operations using the CLI. You can extend it further by integrating automation scripts or IAM policies for better security.

## References
AWS CLI S3 Commands

AWS S3 Documentation
