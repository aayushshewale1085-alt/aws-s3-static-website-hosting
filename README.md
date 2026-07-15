<img width="1920" height="1080" alt="Screenshot 2026-07-15 183805" src="https://github.com/user-attachments/assets/dc9d6129-dab4-4e24-ad01-66acae0f27c8" />
# 🌐 Static Website Hosting on AWS S3

A simple cloud project demonstrating how to host a **static website** using **Amazon S3**. This project covers bucket creation, static website hosting configuration, public access permissions, bucket policy, object upload, and website deployment.

---

## 📌 Project Overview

This project demonstrates how to deploy a static HTML website using Amazon S3 without using any web server like Apache or Nginx.

The website is hosted directly from an S3 bucket configured for Static Website Hosting.

---

## 🚀 AWS Services Used

- Amazon S3
- IAM (AWS Account Permissions)
- S3 Bucket Policy

---

## 🛠️ Technologies Used

- HTML5
- CSS3
- AWS S3

---

# 📁 Project Structure

```
Static-Website-Hosting-on-S3/
│
├── index.html
├── README.md
│
└── images/
    ├── 01-create-bucket.png
    ├── 02-bucket-list.png
    ├── 03-upload-object.png
    ├── 04-static-hosting.png
    ├── 05-live-website.png
    └── 06-replica-bucket.png
```

---

# 🏗️ Architecture

```
                User
                  │
                  ▼
         Browser Request
                  │
                  ▼
        Amazon S3 Bucket
      (Static Website Hosting)
                  │
                  ▼
             index.html
                  │
                  ▼
           Website Displayed
```

---

# 📖 Step-by-Step Implementation

## Step 1: Create an S3 Bucket

- Open AWS Console
- Navigate to Amazon S3
- Click **Create Bucket**
- Choose Region
- Enter a unique bucket name
- Disable Block Public Access (for static hosting)
- Create the bucket

### Screenshot

<img src="https://github.com/user-attachments/assets/5dcd36c9-33de-47a0-8fe8-393834c3518d" width="800"><br><br>

<img src="https://github.com/user-attachments/assets/bdc3a2a1-4e34-4cb0-a081-9dfce11f4ee0" width="800"><br><br>



---

## Step 2: Bucket Created Successfully

After creating the bucket, it appears in the S3 bucket list.

### Screenshot

<img width="800" height="900" alt="Screenshot 2026-07-15 183805" src="https://github.com/user-attachments/assets/72eeaabb-a737-424d-bf21-f2d9825dd4f2" />



---

## Step 3: Upload Website Files

Upload your website files (HTML, CSS, JS).

In this project only:

- index.html

was uploaded.

### Screenshot

<img src="https://github.com/user-attachments/assets/0156f595-8fd5-4678-9ae4-312dd2fcad66" width="800"><br><br>

---

## Step 4: Enable Static Website Hosting

Navigate to

```
Bucket
→ Properties
→ Static Website Hosting
```

Enable:

- Static Website Hosting
- Index Document:
```
index.html
```

Save changes.

### Screenshot

<img src="https://github.com/user-attachments/assets/94c21c8d-6fe0-457d-8e14-87a64bcbef63" width="800"><br><br>
---

## Step 5: Open Website Endpoint

Copy the generated Website Endpoint.

Example:

```
http://bucke+t-name.s3-website-us-east-1.amazonaws.com
```
Open it in the browser.

### Screenshot
<img src="https://github.com/user-attachments/assets/9c8dc61f-4801-4a0c-92d2-ca29f5d32958" width="800"><br><br>

<img src="https://github.com/user-attachments/assets/da1589ad-52cc-4552-9f8c-7018265a92e1" width="800"><br><br>
---

## Step 6: Replica Bucket

To demonstrate object replication manually, a second S3 bucket was created in the **same AWS account** and **same AWS Region**.

### Steps Performed

1. Created a new S3 bucket.
2. Selected the **same AWS Region** as the primary bucket.
3. Uploaded the same website files (`index.html`) to the replica bucket.
4. Enabled **Static Website Hosting** on the replica bucket.
5. Configured the same public access settings and bucket policy.
6. Verified that the replica bucket hosted the same static website successfully.

### Screenshot

<img src="https://github.com/user-attachments/assets/ea47ddb1-660f-4b57-a333-89babcc71eee" width="800"><br><br>

---

## 🔁 Replica Overview

| Feature | Primary Bucket | Replica Bucket |
|---------|----------------|----------------|
| AWS Account | Same | Same |
| AWS Region | Same | Same |
| Website Files | index.html | index.html |
| Static Website Hosting | Enabled | Enabled |
| Bucket Policy | Configured | Configured |
| Public Access | Enabled | Enabled |

---

## 📌 Purpose of Replica Bucket

The replica bucket was created to:

- Demonstrate hosting the same website in another S3 bucket.
- Practice creating multiple S3 buckets in the same AWS account.
- Verify that the website can be deployed consistently across multiple buckets.
- Understand bucket configuration and website hosting on separate buckets.

> **Note:** This project demonstrates a **manual replica** by creating another S3 bucket in the same AWS account and Region. It does **not** use Amazon S3 Cross-Region Replication (CRR) or Same-Region Replication (SRR) rules.

---

# 🔐 Bucket Policy

The following policy allows public read access to the website objects.

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
    }
  ]
}
```

Replace:

```
YOUR_BUCKET_NAME
```

with your bucket name.

---

# 🔓 Public Access Configuration

For static website hosting:

- Disable Block Public Access
- Enable public read access
- Attach Bucket Policy
- Upload website files

---

# 📷 Project Steps

| Step | Description |
|------|-------------|
| ✅ | Create Bucket |
| ✅ | Bucket List |
| ✅ | Upload HTML File |
| ✅ | Enable Static Hosting |
| ✅ | Website Endpoint |
| ✅ | Replica Bucket |

---

# 📚 Learning Outcomes

After completing this project, I learned:

- Creating Amazon S3 Buckets
- Object Upload
- Static Website Hosting
- Bucket Policies
- Public Access Configuration
- Website Endpoints
- AWS Storage Services

---

# 🎯 Future Improvements

- Add CSS and JavaScript files
- Host a portfolio website
- Configure a custom domain
- Enable HTTPS using CloudFront
- Integrate Route 53
- Add Versioning
- Enable Logging

---

# 👨‍💻 Author

**Aayush Shewale**

Cloud & DevOps Enthusiast

GitHub: https://github.com/aayushshewale1085-alt

LinkedIn: https://www.linkedin.com/in/aayush-shewale-4b194732b/

---

# ⭐ If you found this project useful

Give this repository a ⭐ on GitHub.
