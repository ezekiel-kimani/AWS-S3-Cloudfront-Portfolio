# AWS Static Website Hosting with Amazon S3 and Amazon CloudFront

## Project Overview

This project involved deploying my professional portfolio using Amazon S3 and Amazon CloudFront. The portfolio presents my professional profile, qualifications, certifications, skills, projects, and career development.

The objective was to establish a publicly accessible online presence while gaining practical experience with AWS storage, static website hosting, content delivery, and access control.

**Live Website:** https://d3hh2pnu76p30u.cloudfront.net

## Project Objectives

- Deploy a static website using Amazon S3.
- Create and configure an Amazon CloudFront distribution.
- Configure the S3 website endpoint as the CloudFront origin.
- Provide HTTPS access through the CloudFront distribution.
- Understand how CloudFront distributes and caches website content.
- Gain practical experience with AWS configuration, deployment, testing, and troubleshooting.

## AWS Services Used

### 1. Amazon S3

Amazon S3 was used to store the static website files and host the website through its static website hosting endpoint.

**Key activities:**
- Created an S3 bucket for the website.
- Uploaded the website files.
- Enabled static website hosting.
- Identified the S3 website endpoint for use as the CloudFront origin.

### 2. Amazon CloudFront

Amazon CloudFront was used to distribute website content through a CloudFront distribution, providing the public HTTPS entry point for the portfolio.

**Key activities:**
- Created and configured a CloudFront distribution.
- Configured the S3 static website endpoint as the origin.
- Used the CloudFront distribution domain to access the website over HTTPS.
- Tested website delivery through the distribution.
- Corrected an incorrect origin path that affected content delivery.

CloudFront can cache website content at edge locations closer to viewers. When content is cached, subsequent requests can be served without retrieving that content from the origin again, depending on the cache configuration.

**CloudFront distribution domain:**  
https://d3hh2pnu76p30u.cloudfront.net

**S3 website endpoint:**  
http://ezekiel-kimani-static-web.s3-website-us-east-1.amazonaws.com

## Architecture Overview

The website follows this delivery path:

**Visitor → Amazon CloudFront Distribution (HTTPS) → Amazon S3 Static Website Endpoint**

1. A visitor requests the website using the CloudFront distribution domain.
2. CloudFront serves cached content when available.
3. When content is not available in the cache, CloudFront retrieves it from the configured S3 website origin.
4. CloudFront delivers the content to the visitor over HTTPS.

This architecture separates website storage from content delivery and provides a public HTTPS entry point for visitors.

## Security and Architecture Considerations

The project provided an opportunity to consider how access to website content should be controlled.

For a more secure production-oriented design, I would evaluate using an S3 REST API endpoint with **Amazon CloudFront Origin Access Control (OAC)**. OAC allows CloudFront to access a private S3 bucket through an appropriate bucket policy, preventing direct public access to the bucket's objects when the permissions are configured correctly.

The current architecture uses an S3 static website endpoint, which does not support OAC. Implementing this improvement would require changing the origin configuration and reviewing the bucket permissions. OAC is a proposed improvement, not a feature claimed as implemented in this project.

## Testing and Troubleshooting

During testing, I identified an incorrect path in the CloudFront origin configuration that affected website content delivery. I corrected the path and retested the website through the CloudFront distribution domain to confirm that the content was accessible.

This experience reinforced the importance of checking the distribution's origin settings when troubleshooting content delivery between Amazon S3 and Amazon CloudFront.

## Project Outcomes

The project resulted in a publicly accessible professional portfolio hosted using AWS services.

Through this project, I gained practical experience with:

- Amazon S3 static website hosting.
- CloudFront distribution creation and configuration.
- Origin configuration and S3 website endpoints.
- HTTPS content delivery.
- CloudFront caching concepts.
- AWS deployment testing and troubleshooting.

The project strengthened my understanding of how Amazon S3 and Amazon CloudFront work together to publish and distribute website content.

## Future Improvement

A logical next step would be to recreate the website infrastructure using Infrastructure as Code (IaC), such as AWS CloudFormation or Terraform. This would provide practical experience defining, deploying, and managing the resources through reusable configuration rather than relying entirely on manual setup.

## Conclusion

This project provided hands-on experience deploying a static website using Amazon S3 and Amazon CloudFront. It established a public online presence for my professional portfolio while strengthening my understanding of storage, distribution configuration, HTTPS delivery, caching, and troubleshooting.

It also provided a foundation for exploring more advanced AWS practices, including access control and infrastructure automation.
