# Deploying a Static Website Using S3 and CloudFront

This repository documents how to host a static website on AWS using an S3 bucket and deliver it globally using Amazon CloudFront.  
It includes a sample site, deployment steps, an architecture diagram, and placeholder folders for screenshots.

---

## Project Structure

s3-cloudfront-static-website/
│
├── docs/
│   ├── architecture.png
│   ├── screenshots/
│   │   └── privately hosted
│   │   └── publicly hosted
│   └── deployment-steps.md
│
├── index.html
├── README.md
└── LICENSE

---

## What Is a Static Website?

A static website serves fixed files such as HTML, CSS, JavaScript, and JSON.  
The browser loads the files directly without backend code or a database.

### Typical examples
- Personal portfolios  
- Company info pages  
- Documentation sites  

---

## Why Host on S3 + CloudFront?

- No servers to manage  
- Cost effective  
- Secure when using Origin Access Control (OAC)  
- Fast global delivery using CloudFront edge caching  

---

## Architecture Diagram

+-------------------+
| End User |
| Browser/Client |
+---------+---------+
|
v
+-------------------+
| CloudFront CDN |
| (Edge Locations) |
+---------+---------+
|
v
+------------------------------+
| Origin Access Control (OAC) |
| Provides secure access |
+--------------+---------------+
|
v
+------------------------------+
| S3 Bucket (Private) |
| Stores HTML/CSS/JS files |
+------------------------------+

The S3 bucket may be public or private.  
If private, CloudFront uses OAC to access objects securely.

---

## Quick Usage

1. Read `docs/deployment-steps.md` for the full AWS console workflow.  
2. Add the architecture diagram to `docs/architecture.png`.  
3. Upload CloudFront and S3 screenshots to `docs/screenshots/`.  
4. Push updates to GitHub after testing.

---

## Cleanup Instructions

To avoid charges on your AWS Free Tier:

- Delete the CloudFront distribution  
- Empty and delete the S3 bucket  
- Remove any extra AWS resources used during testing  

---

## License

This project is licensed under the MIT License.  
See the `LICENSE` file for details.



