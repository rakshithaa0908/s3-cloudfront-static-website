
---
# Deployment Steps for S3 + CloudFront Static Website
This guide walks through hosting a static website on Amazon S3 and delivering it globally via CloudFront using Origin Access Control (OAC).

---
## Step 1: Create S3 Bucket
1. Open the AWS Console → Search for S3  
2. Create bucket  
3. Enter a unique bucket name  
4. Keep block public access ON if using OAC  
5. Create bucket  
---
## Step 2: Upload Website Files
1. Open the bucket  
2. Upload `index.html` (and other static files)  
---
## Step 3: Create CloudFront Distribution
1. Open CloudFront
2. Click **Create distribution**
3. Origin type → Amazon S3
4. Select your bucket
5. Under **Origin Access** → select **Origin Access Control (OAC)**
6. Click **Create new OAC** → enter a name → click **Create**
7. Click **Create distribution**
---
## Step 4: Update S3 Bucket Policy
1. After distribution is created, CloudFront will prompt you to update the S3 bucket policy
2. Click **Copy policy**
3. Open S3 → your bucket → **Permissions** → **Bucket policy**
4. Paste the copied policy
5. Click **Save changes**
---
## Step 5: Test Website
Use the CloudFront domain to access your website:
```
https://<your-distribution-id>.cloudfront.net/index.html
```
> Note: It may take a few minutes for the distribution to deploy before the URL becomes accessible.

---
> ✅ Deployment complete. Your static website is now hosted on S3 and delivered globally via CloudFront.


