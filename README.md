# 🚀 Automated Infrastructure Deployment with AWS CloudFormation and CodePipeline

**👤 Name:** Rishikumar Patel
**🆔 Student ID:** 8972657
**📅 Date:** July 17, 2025

---

## 📌 Overview

This project demonstrates how to automate infrastructure deployment using AWS CloudFormation and AWS CodePipeline. It provisions an S3 bucket using a CloudFormation template and sets up a CI/CD pipeline to automatically deploy any changes pushed to a GitHub repository.

---

## 📁 CloudFormation Template

- **Resource:** S3 Bucket
- **Parameters:**
  - `BucketName` – Name of the bucket to create
  - `VersioningStatus` – Enabled or Suspended
- **Tags:** Owner: Rishikumar 💘
- **Validation Command:**
  ```bash
  aws cloudformation validate-template --template-body file://s3-bucket-template.yaml
  ```

---

## 💻 GitHub Repository

- Repository: `rishhi-patel/cloudformation-pipeline`
- Branch: `main`
- Contains: `s3-bucket-template.yaml`

---

## 🔧 CodePipeline Configuration

- **Source Stage:**
  - Connected to GitHub (main branch)
- **Deploy Stage:**
  - Provider: AWS CloudFormation
  - Stack Name: `s3-bucket-stack`
  - Template: `s3-bucket-template.yaml`
  - **ParameterOverrides:**
    ```json
    {
      "BucketName": "8972657-rishhi-patel",
      "VersioningStatus": "Enabled"
    }
    ```

---

## 🔁 Automation Trigger

- A change (adding tags) was pushed to the main branch.
- CodePipeline auto-triggered and deployed the updated template.

---

## ✅ Verification & Cleanup

- Verified S3 bucket creation in the AWS Console
- Confirmed versioning and tags
- Deleted the CloudFormation stack post-validation

---

## 📸 Screenshots (to attach in report or folder)

### Template validation
  <img width="2560" height="1600" alt="image" src="https://github.com/user-attachments/assets/e52896d5-6905-4a30-b363-3d1beec1997f" />
  
### CodePipeline run logs

<img width="2560" height="1600" alt="image" src="https://github.com/user-attachments/assets/9ac43943-a4e8-41ed-8baa-14c7fc91da42" />

<img width="2560" height="1600" alt="image" src="https://github.com/user-attachments/assets/a828b787-5317-4e87-8bc2-8bd2c9ad4c4e" />

### S3 bucket confirmation
  <img width="2560" height="1600" alt="image" src="https://github.com/user-attachments/assets/a45ec62b-2262-4ea6-b5ac-9ed2ec6b490c" />

  

---

## 📝 Notes

- Ensure you create a proper IAM role for CloudFormation with full access.
- Validate the template before pushing to avoid errors in the pipeline.

---
