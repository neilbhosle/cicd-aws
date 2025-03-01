# AWS CI/CD Pipeline for Static Website Deployment

This project demonstrates how to set up a **CI/CD pipeline** using **AWS CodePipeline** to automatically deploy a static website to an **Amazon S3 bucket**. The pipeline is triggered whenever changes are pushed to a **GitHub repository**.

---

## 🚀 Features

- **Automated Deployment**: Automatically deploys changes to an S3 bucket when code is pushed to the GitHub repository.
- **Static Website Hosting**: The S3 bucket is configured to host a static website.
- **CI/CD Pipeline**: Uses AWS CodePipeline to manage the deployment process.
- **Scalable and Cost-Effective**: Leverages AWS Free Tier for low-cost hosting.

---

## 🛠️ Prerequisites

Before you begin, ensure you have the following:

1. **AWS Account**: Sign up for an AWS account if you don’t have one.
2. **GitHub Repository**: A GitHub repository containing your static website files (`index.html`, `style.css`, etc.).
3. **AWS CLI** (optional): For managing AWS resources from the command line.
4. **Basic Knowledge** of AWS services (S3, CodePipeline) and GitHub.

---

## 🧰 Tools and Services Used

- **Amazon S3**: Hosts the static website.
- **AWS CodePipeline**: Automates the CI/CD process.
- **GitHub**: Stores the source code and triggers the pipeline.
- **AWS IAM**: Manages permissions for the pipeline.

---

## 🚀 Setup Instructions

### 1. Create an S3 Bucket
1. Go to the **S3 Console** in AWS.
2. Create a new bucket (e.g., `aws-cicd-static-website`).
3. Enable **Static Website Hosting** in the bucket properties.
4. Set the bucket policy to make it publicly accessible:
   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Sid": "PublicReadGetObject",
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::aws-cicd-static-website/*"
           }
       ]
   }
