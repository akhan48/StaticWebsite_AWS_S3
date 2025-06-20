# 📦 Static Website Hosting on Amazon S3

This project demonstrates how to host a **static website** on **Amazon S3** with proper permissions, a default display page (`index.html`), and a custom error page (`error.html`).

## 🚀 Project Overview

Amazon S3 (Simple Storage Service) provides a simple and cost-effective way to host static websites. In this project, a static website was successfully hosted with:

- `index.html`: Main landing page (default page)
- `error.html`: Custom error page for 4XX errors
- Correct bucket permissions and static website hosting configuration

## 🧰 Technologies Used

- **Amazon S3**
- **HTML**
- **AWS Management Console**

## ✅ Steps to Reproduce

1. **Create an S3 Bucket**
   - Bucket name must be globally unique.
   - Uncheck “Block all public access” (for public website hosting).

2. **Upload Website Files**
   - Upload `index.html` and `error.html` to the bucket.

3. **Enable Static Website Hosting**
   - Go to **Properties** → **Static website hosting**
   - Enable it and set:
     - Index document: `index.html`
     - Error document: `error.html`

4. **Set Bucket Policy for Public Access**
   - Add a bucket policy like below to allow public reads:

     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Sid": "PublicReadGetObject",
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::your-bucket-name/*"
         }
       ]
     }
     ```

5. **Access the Website**
   - Use the **S3 Static Website Endpoint** to view your hosted website.
   - # http://cloudresume2025.s3-website-us-east-1.amazonaws.com/

## 🌐 Live Demo
 See in screenshots folder

## 📂 File Structure
project-folder/
│
├── index.html # Main landing page
├── error.html # Custom error page
├── Screenshots # folder with live website screenshots
└── README.md # Project documentation

## 📌 Notes

- Ensure public access is enabled via both bucket policy and permissions.
- AWS S3 does not support server-side scripting (PHP, Python, etc.)—only static content.

## 📧 Contact

For any questions or suggestions, feel free to reach out!

---

> 💡 **Tip**: Use Route 53 or another DNS service to map a custom domain to your S3 website for a more professional URL.
