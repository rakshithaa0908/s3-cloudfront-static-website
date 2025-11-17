
---

# **deployment-steps.md (Create this file inside /docs)**

# Deployment Steps for S3 + CloudFront Static Website

## Step 1: Create S3 Bucket
1. Open the AWS Console → Search for S3  
2. Create bucket  
3. Enter a unique bucket name  
4. Keep block public access ON if using OAC  
5. Create bucket  

## Step 2: Upload Website Files
1. Open the bucket  
2. Upload `index.html` (and other static files)  

## Step 3: Create CloudFront Distribution
1. Open CloudFront  
2. Choose “Create distribution”  
3. Origin type → Amazon S3  
4. Select the bucket  
5. Enable OAC for private hosting  
6. Create distribution  

## Step 4: Update S3 Bucket Policy
1. Open CloudFront → Origins → Create OAC  
2. Copy the generated policy  
3. Open S3 → Permissions → Bucket policy  
4. Paste the policy  

## Step 5: Test Website
Use the CloudFront domain:
https://<your-distribution-id>.cloudfront.net/index.html




