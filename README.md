# Static Website Hosted On AWS Utilising S3, CloudFront, ACM, Route 53

## Project Overview

The creation of a static website that will provide quick access to the projects that I will be working on to try and get my first cloud engineer role. Utlising multiple AWS services in order to create a cost effective, secure, highly availabile and low latency website that can be accessed from anywhere. I used S3 for cost effective file storage, a CloudFront distribution to prevent the S3 bucket being accessed by the public and reduce latency when trying to access, paired with ACM in order to ensure traffic is HTTPS, and route 53 to register my own domain and make it accessible on the internet. 


## Features

* Cost-effective and secure storage of static files and content in Amazon S3, accessed exclusively through a CloudFront Distribution. 
* Content Delivery Network (CDN) for fast global access provided by CloudFront.
* Secure communication via HTTPS (SSL/TLS certificate) using Amazon Certificate Manager paired with CloudFront behaviours.
* Purchase of a domain through route 53 and making it globablly accessible by creating A-records to pair to CloudFront resources.

## Architecture

* [Architecture Diagram](docs/architecture/static-web-architecture.png)
* S3
    - Storing files on S3 is very cost effective as the charges are very reasonable.
    - Secure file storage due to no one being able to access S3 outside of the AWS console without specific policies allowing it.
    - High availability. S3 is automatically replicated across multiple AZs also making highly redundant.
* Route 53
    - Allows you to register domains to use for your static website.
    - Using various DNS records (such as alias records) you can link your hosted zone to various AWS resources such as CloudFront.
* AWS Certificate Manager
    - Allows you to create free SSL/TLS certificates to increase the security of your website. 
* CloudFront
    - Content delivery network that reduces latency by storing cached data in edge locations.
    - Using behaviours you can ensure that the correct network protcols are being used i.e. HTTPS instead of HTTP.
    - Provides an extra layer of security to your data as CloudFront accesses your S3 bucket instead of any external connection.
 
## Technologies Used

* Cloud Platform: AWS.
* AWS Services: S3, CloudFront, AWS Certificate Manager (ACM), Route 53.
* Languages/Tools: HTML, CSS.

## Prerequisites

* Mandatory prerequisites.
    - AWS account.
    - IAM user with programmatic access and permissions to manage S3, ClouFront, ACM, Route 53 and IAM resources.
    - Money to purchase a domain or access to a registered domain.


## Deployment Steps

1. S3
    - Create your S3 bucket. Ensure the bucket has a globally unique name and is in the region for your project (Best practice would be to match your bucket to your domain name).
    - Upload the index.html file for the website. 
2. ACM
    - Switch your region to us-east-1 and request a certificate (ensure you select public certificate).
    - Add the required domain names.
    - Select DNS validation for the validation method.

3. Create a CloudFront Distribution.
    - Select Amazon S3 and select your s3 bucket as the origin.
    - Use the CloudFront recommended origin settings.
    - For this scale of project WAF is not needed. 
    - Edit the settings of the distribution, ensure the custom SSL is asigned, the default root object is 'index.html' and the default behaviour is set to redirect http to https.

4. Update S3 Bucket Policy.
    - Copy the origin Access control bucket policy that is generated from CloudFront and paste it into your S3 bucket policy.

5. Map your domain.
    - Go to your Route 53 hosted zone.
    - Create DNS records that point to CloudFront. 

6. Visit your new static website.
    - The domain you reserved should now be accessible.

* For Detailed Instructions and Visual Proof:
 [Detailed deployment guide with screenshots](docs/detailed-deployment-guide.md)

Deployed URL
* [https://tjt.org.uk]

## Visuals Of Finished Project
    
* Finished website: [Website Homepage](docs/screenshots/screenshots/finished-project-photos/finished-website.png)
* CloudFront distribution: [CloudFront Distribution](docs/screenshots/finished-project-photos/cloudfront-distribution.png)
* Generated certificates: [ACM certificates](docs/screenshots/finished-project-photos/generated-certificates.png)
* Finished S3 bucket: [S3 Bucket](docs/screenshots/finished-project-photos/s3-bucket.png)

## Lessons Learned & Challenges Overcome

I really enjoyed this project. As a start to my professional cloud journey getting experience purchasing a domain and creating a static website is a great start. It allowed me utilise some of AWS core features for content delivery, DNS and file storage. 

I learned some key facts about AWS that were unexpected. For example, in order to generate ACM certificates they must be created in us-east-1 and then assigned to the CloudFront distribution required. I also learned that to ensure no overlapp it is essential that your S3 bucket must not allow any public access and be locked down apart from the policy that allows CloudFront access. I ran into an issue whilst creating the website where CloudFront was not enforcing HTTPS. This is where I learned how to modify distribution behvaviours and how granular the CloudFront controls are. I was unaware that the assigning a default root object was essential for a static web page. Utilising all these changes led me to the invalidation tab which clears your caches and ensures that the most recent files from your origin locations are distributed. 

## Future Enhancements

As this is my first ever project it's simple but effective. From a visual perspective I could utilise images, fonts and colours to make the page more presentable. The process of creating the website can be sped up through automation. I could use AWS CodePipeline, CodeBuild and S3 sync to ensure every commit to my github repository automatically updates the website content.I could also configure monitoring and logging by sending the access logs to a S3 bucket. Security could also be improved by utilising AWS WAF to protect the website web exploits. 

## Tyrelle Trerise

* [https://www.linkedin.com/in/tyrelle-trerise-9766b9108/]
* [https://tjtrerise.github.io/TTrerise.Portfolio.io/]
* [https://tjt.org.uk]

