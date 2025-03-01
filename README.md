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

---

## 2. Set Up AWS CodePipeline
Go to the CodePipeline Console in AWS.

- Create a new pipeline (e.g., MyStaticWebsitePipeline).

- Configure the Source Stage:

- Connect to your GitHub repository.

- Select the branch (e.g., main).

- Skip the Build Stage (not needed for static websites).

- Configure the Deploy Stage:

- Choose Amazon S3 as the deployment provider.

- Select your S3 bucket.

- Enable Extract file before deploy.

- Review and create the pipeline.

## 3. Test the Pipeline
Make a change to your index.html file in the GitHub repository.

Push the changes to the repository.

The pipeline will automatically trigger and deploy the changes to the S3 bucket.

Visit the S3 bucket website endpoint to see the updated website:

```json
http://aws-cicd-static-website.s3-website-us-east-1.amazonaws.com
```
---

📂 Project Structure
```json
my-static-website/
├── index.html          # Main HTML file
├── style.css           # CSS file for styling
├── script.js           # JavaScript file (optional)
└── README.md           # Project documentation
```
---
💡 Customization
Add a Custom Domain: Use Amazon Route 53 to map a custom domain to your S3 bucket.

Enable HTTPS: Use Amazon CloudFront to serve your website over HTTPS.

Add More Features: Extend the website with additional pages, a blog, or a contact form.

---

📜 License
This project is licensed under the MIT License. See the LICENSE file for details.

---

🙏 Acknowledgments

AWS Documentation

GitHub Actions Documentation
