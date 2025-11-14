# Deploying a Static Website Using S3 and CloudFront

This repository documents how to host a static website on AWS using an S3 bucket and deliver it globally using Amazon CloudFront (CDN).  
It includes a sample site, deployment steps, an architecture diagram, and screenshot placeholders.

---

## Project structure

project-folder/
│
├── docs/
│ ├── architecture.png
│ ├── screenshots/
│ │ └── (add your AWS console screenshots here)
│ └── deployment-steps.md
│
├── index.html (optional sample page)
├── README.md
└── LICENSE

---


---

## What Is a Static Website?

A static website serves fixed files like HTML, CSS, JavaScript, and JSON. The browser loads the content directly without backend processing or a database.

Typical examples:
- Personal portfolio sites  
- Company information pages  
- Documentation pages  

### Why Host on S3 + CloudFront?

- No servers to manage  
- Cost effective  
- Highly secure with OAC  
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

---

The S3 bucket can be public or private.  
If private, CloudFront uses OAC to access the files securely.

---

## Quick Usage

1. Read `docs/deployment-steps.md` for the complete AWS console walkthrough.  
2. Upload `architecture.png` and screenshots under `docs/screenshots/`.  
3. Push updates to GitHub as you refine the project.  

---

## Cleanup Instructions

To avoid charges on your AWS Free Tier:
- Delete the CloudFront distribution  
- Then delete the S3 bucket  
- Remove any extra resources used during testing  

---

## License

This project is licensed under the MIT License. See the LICENSE file for details.



