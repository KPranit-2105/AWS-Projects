# Static Web Hosting with Amazon S3

This project demonstrates how to host a static website using **Amazon S3**, a simple and scalable cloud storage service provided by AWS. The guide covers configuring an S3 bucket for static web hosting, uploading website files, and setting up permissions for public access.

---

## Features

- Host static HTML, CSS, and JavaScript files.
- No server maintenance required.
- Highly scalable and cost-effective.
- Support for custom domain configuration (optional).
- Built-in redundancy and high availability.

---

## Prerequisites

To follow along with this project, you need:

- An active [AWS account](https://aws.amazon.com/).
- Basic knowledge of HTML/CSS/JavaScript (optional but helpful).
- AWS CLI (optional, for automated deployment).

---

## Steps to Set Up Static Web Hosting

### 1. **Create an S3 Bucket**
   - Go to the [Amazon S3 console](https://s3.console.aws.amazon.com/).
   - Click on **Create bucket**.
   - Enter a unique bucket name and select a region.
   - Uncheck "Block all public access" (required for public website hosting).
   - Create the bucket.

### 2. **Upload Your Website Files**
   - Open your S3 bucket.
   - Click on **Upload**.
   - Drag and drop your static website files (e.g., `index.html`, `style.css`).
   - Click **Upload**.

### 3. **Enable Static Website Hosting**
   - Navigate to the **Properties** tab of your S3 bucket.
   - Scroll to the **Static website hosting** section and enable it.
   - Specify your **index document** (e.g., `index.html`) and error document (e.g., `error.html`).
   - Save the configuration.

### 4. **Set Bucket Permissions**
   - Navigate to the **Permissions** tab.
   - Under **Bucket Policy**, add the following policy to allow public access:
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
     ```
   - Replace `your-bucket-name` with your actual bucket name.

### 5. **Access Your Website**
   - Copy the **Bucket Website Endpoint** from the **Static website hosting** section.
   - Paste the URL into your browser to access your static website.

---

## Optional Enhancements

1. **Custom Domain with Route 53**  
   - Use AWS Route 53 to configure a custom domain name for your website.
   - Update the DNS settings with the endpoint of your S3 bucket.

2. **HTTPS with Amazon CloudFront**  
   - Use Amazon CloudFront (CDN) to enable HTTPS and improve website performance.

3. **Automated Deployment with AWS CLI**  
   - Automate the upload process using the AWS CLI with a command like:
     ```bash
     aws s3 sync ./website-folder s3://your-bucket-name
     ```

---

## Technologies Used

- **Amazon S3**: For hosting the static website.
- **AWS Management Console**: For bucket and website configuration.
- **HTML/CSS/JavaScript**: For the website content.

---

## Contributing

Contributions are welcome! Please fork this repository and submit a pull request with your changes. For major updates, please open an issue to discuss your proposed changes.

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

## Author

Pranit Kolamkar  
Cloud Computing Enthusiast  
[GitHub](https://github.com/KPranit-2105/AWS-Projects) | [LinkedIn](www.linkedin.com/in/pranit-kolamkar110274)

---
