# techcrush_website_hosting

Step 1: Created an AWS Account

Go to AWS Console


Step 2: Create an S3 Bucket

Navigate to Services → S3

Click Create bucket

Bucket name:techcrush-bucket

Region: useast-1

Bucket settings:

Uncheck Block all public access (we need public access for a static site)

Acknowledge warning about public access

Click Create bucket

Step 3: Upload the index.html file


Click Upload

Step 4: Enable Static Website Hosting


Select Host a static website

Index document: index.html

Error document: error.html (optional)

Click Save

Step 5: Make Files Public

Go to Permissions → Bucket Policy

Click Edit and paste this JSON, replacing <bucket-name> with your bucket name:

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::<bucket-name>/*"
        }
    ]
}


Click Save

This makes all files in the bucket publicly readable.

copied the url and it worked

