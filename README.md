# Deploying a Static Website Using Amazon S3 and CloudFront

This project explains how to host a static website on AWS using an S3 bucket and deliver it globally using Amazon CloudFront.  
It covers how static sites work, why companies use them, key AWS services involved, and step-by-step deployment guidance.

---

## What Is Static Website Hosting?

A static website contains fixed files such as HTML, CSS, JavaScript, and JSON.  
The server delivers these files directly to the browser without running backend code or connecting to a database.

Examples:
- Portfolio websites  
- Company information pages  
- Simple documentation sites  

### Why Companies Use Static Websites
- No servers to manage  
- Low cost  
- High security  
- Fast performance  

---

## Static vs Dynamic Websites

| Static Website | Dynamic Website |
|----------------|-----------------|
| Fixed content | Content changes dynamically |
| No server-side code | Uses backend languages (Python, Node.js, Java) |
| Fast and cheap | Slower and more expensive |

---

## AWS Services Used

### Amazon S3 (Simple Storage Service)
Used to store and retrieve data over the internet.

Key points:
- Bucket names must be globally unique  
- General Purpose buckets: up to 10,000  
- Pay only for what you use  
- No upfront cost  

**How to secure an S3 bucket**
- Block Public Access  
- Use ACL or IAM permissions  
- Apply bucket policies  
- Enable encryption  

---

### Amazon CloudFront (CDN)

CloudFront caches your content in global edge locations so users can access it quickly from anywhere.

Benefits:
- Faster content delivery  
- Pay-as-you-go  
- Highly available  
- Works with S3 using Origin Access Control (OAC)  

---

## Project Structure

```markdown
s3-cloudfront-static-website/
│
├── docs/
│   ├── deployment-steps.md
│   └── screenshots/
│       ├── architecture.png
│       ├── privately_hosted.png
│       └── publicly_hosted.png
│
├── README.md
└── index.html

---

## Architecture Diagram

Below is the architecture of the static website hosted on S3 and delivered through CloudFront:

![Architecture Diagram](docs/architecture.png)

---

## Screenshot: Privately Hosted (OAC Enabled)

This setup uses Origin Access Control so the S3 bucket remains private.

![Privately Hosted Setup](docs/privately_hosted.png)

---

## Screenshot: Publicly Hosted (No OAC)

This version allows public access directly from the S3 bucket.

![Publicly Hosted Setup](docs/publicly_hosted.png)

---

## Deployment Steps (Console)

1. Open S3 → Create a bucket  
   Example name: `demo-bucket-13-11-25`

2. Upload `index.html` to the bucket.

3. Open CloudFront → Create Distribution  
   - Origin type: Amazon S3  
   - Select your bucket  
   - Enable security protections (WAF optional)  
   - Create distribution  

4. After creation, open the distribution → Origins tab  
   - Create new origin  
   - Set Origin Access Control (OAC)  
   - Copy the generated bucket policy  

5. Go to S3 → Permissions → Bucket Policy  
   - Paste the policy  
   - Save changes  

6. Copy the CloudFront domain URL  
   Example:  
   `d123abcd.cloudfront.net/index.html`

7. If origin access is Public, no bucket policy is required.

---

##License

This project is licensed under the MIT License.

