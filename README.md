<<<<<<< HEAD
# Project Title: [Your Project Name Here, e.g., "My Personal Portfolio Website"]

## Project Overview

The creation of a static website that will provide quick access to the projects that I will be working on to try and get my first cloud engineer role. Utlising multiple AWS services in order to create a cost effective, secure, highly availabile and low latency website that can be accessed from anywhere. I used S3 for cost effective file storage, a CloudFront distribution to prevent the S3 bucket being accessed by the public and reduce latency when trying to access, paired with ACM in order to ensure traffic is HTTPS, and route 53 to register my own domain and make it accessible on the internet. 


## Features

* Cost-effective and secure storage of static files and content in Amazon S3, accessed exclusively through a CloudFront Distribution. 
* Content Delivery Network (CDN) for fast global access provided by CloudFront.
* Secure communication via HTTPS (SSL/TLS certificate) using Amazon Certificate Manager paired with CloudFront behaviours.
* Purchase of a domain through route 53 and making it globablly accessible by creating A-records to pair to CloudFront resources.

## Architecture

* A high-level description of the solution architecture.
* [Architecture Diagram](docs/static-web-architecture.png)`).
* Briefly explain the role of each major AWS service (S3, CloudFront, ACM, Route 53 if used).

## Technologies Used

* List all key technologies and tools used:
    * **Cloud Platform:** AWS
    * **AWS Services:** S3, CloudFront, AWS Certificate Manager (ACM), Route 53 (if applicable), IAM
    * **Infrastructure as Code (IaC):** [Terraform / AWS CloudFormation]
    * **Version Control:** Git
    * **Languages/Tools:** HTML, CSS, JavaScript (for the website content itself)

## Prerequisites

* List what a user needs to have installed or configured *before* they can deploy your project.
    * AWS Account with appropriate permissions
    * AWS CLI configured
    * [Terraform / AWS CLI / cfn-cli] installed (depending on your IaC choice)
    * A registered domain name (if using custom domain)

## Deployment Steps

* Provide a clear, basic, step-by-step guide to deploy the project. Keep it concise.
* Use numbered lists and code blocks for commands.
* **Important:** If you have highly detailed steps with many screenshots, link to a more comprehensive guide in your `docs/` directory.

    1.  **Clone the Repository:**
        ```bash
        git clone [https://github.com/yourusername/your-static-website-project.git](https://github.com/yourusername/your-static-website-project.git)
        cd your-static-website-project
        ```
        * *(Optional: Include a single key screenshot here of cloning the repo or the project directory structure after cloning)*

    2.  **Configure AWS Credentials:**
        * Brief instruction on ensuring AWS CLI is configured.

    3.  **Deploy Infrastructure (using [Terraform / CloudFormation]):**
        * Provide the commands to initialize, plan, and apply your IaC.
        ```bash
        # Example for Terraform
        cd infra
        terraform init
        terraform plan
        terraform apply --auto-approve
        ```
        * *(Optional: Include a single key screenshot here of a successful IaC deployment output)*

    4.  **Upload Website Content to S3:**
        * Brief instructions on how to sync your website content to the S3 bucket created by IaC.
        ```bash
        aws s3 sync src/ s3://your-s3-bucket-name --delete
        ```

    5.  **Access the Website:**
        * Provide the CloudFront distribution URL or your custom domain.
        * *(Optional: Include a screenshot of the live website)*

* **For Detailed Instructions and Visual Proof:**
    * `[View the detailed deployment guide with screenshots here](docs/detailed-deployment-guide.md)`

## Live Demo / Deployed URL (if applicable)

* `[Link to your live static website here]`

## Screenshots / Visuals (if embedded)

* You can embed key screenshots directly here if they highlight major features or the final product.
    * Example: `![Website Homepage](docs/screenshots/homepage.png)`
    * Example: `![CloudFront Distribution](docs/screenshots/cloudfront-distribution.png)`

## Lessons Learned & Challenges Overcome

* Reflect on your experience. This is crucial for a portfolio!
* What did you learn during this project? (e.g., nuances of S3 bucket policies, CloudFront caching behaviors, ACM certificate validation).
* What challenges did you face, and how did you overcome them? (e.g., DNS propagation issues, HTTPS redirection, cache invalidation).

## Future Enhancements (Optional)

* Ideas for future improvements or additional features you might add.
    * Example: Add a contact form using Lambda and API Gateway.
    * Example: Implement CI/CD pipeline for automated deployments.

## Author

* Your Name
* [Your LinkedIn Profile Link]
* [Your GitHub Profile Link]
* [Your Personal Website/Portfolio Link (if applicable)]

---
=======
Creating my static portfolio blog on S3, served via CloudFront with HTTPS. Registering a domain and configuring DNS with Route 53. 
>>>>>>> 666c8c8bc4361fa1c1de86293ad25c22d0ac8d7e
