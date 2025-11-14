# Deploying a Static Website Using S3 and CloudFront

This repository documents how to host a static website on AWS using an S3 bucket and deliver it globally using Amazon CloudFront (CDN).  
It includes a sample site, deployment steps, an architecture diagram, and screenshot placeholders.

---

## Project structure


---

## What is a static website?
A static website serves fixed files (HTML, CSS, JS, JSON). No server-side code or database runs when serving the site. Typical examples: portfolio pages and simple company information sites.

### Why S3 + CloudFront?
- No servers to manage  
- Cost effective (pay only for what you use)  
- Highly secure when using Origin Access Control (OAC)  
- Fast global delivery via CloudFront edge caching

---

## Quick usage
1. Read docs/deployment-steps.md for full console / CLI steps.  
2. View docs/architecture.png for the architecture diagram.  
3. Upload screenshots to docs/screenshots/ to show proof of deployment.

---

## Clean up
Remember to delete CloudFront distributions and S3 buckets after testing to avoid charges.

---

## License
This project is licensed under the MIT License. See LICENSE for details.
