# Deploying My PortFolio  on AWS S3

- [Project Link](#)
- [Documentation Link](https://aashishsec.github.io/CloudProjects/AWS/S3-Portfolio/)
 

### Set up an AWS S3 instance

1. Create an IAM user with s3 full access.
2. Login to that IAM User.
3. Now Let's Start Creating S3 bucket. 
4. I named my bucket as `myprofolio-31jan`
5. Keep settings as default and Create the bucket we will change them accordingly.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/f16358b4-57b3-4134-a1ed-26e1c71f9ac8)
6. Let's upload out portfolio files into the bucket.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/af80a074-bcaa-41bb-bc9d-7226de7f9b6d)
7. To host our portfolio to public we have to change some settings in S3 bucket.
- Block public access should be off
- We have to make Bucket policy that should be avilabile to open internet.
- We also have to enable Static website hosting.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/996b23b9-ffb4-4611-ae97-b0704752531f)
8.  We have to uncheck Block public access.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/c27b10a0-5cf0-4b92-9ecd-c69413c46113)
9. We have to make a bucket policy.
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                "s3:GetObject"
            ],
            "Resource": [
                "arn:aws:s3:::myprofolio-31jan/*"
            ]
        }
    ]
}

```
10. Enable the static website hosting and add index document.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/b0d07f21-ebcc-4f1c-af9e-47422928459d)
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/ad0b749e-4b8b-4a5c-9723-5f28cb5616ca)
12. Now we can able to access the our portfolio.
- [Link](https://myprofolio-31jan.s3.ap-south-1.amazonaws.com/PortFolio/index.html)
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/d2894467-6228-41f6-b8d3-5f1e5f9d997f)
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/133cc5c9-f74c-4dc8-9580-f626760aab0f)

### PortFolio App S3 Project is deployed on AWS 🎉
---

