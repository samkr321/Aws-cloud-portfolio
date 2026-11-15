# AWS S3 Secure Storage with IAM Role-Based Access

## Project Overview
Implemented a secure AWS S3 storage solution using IAM role-based access from an Amazon EC2 instance.

## AWS Services Used
- Amazon S3
- AWS IAM
- Amazon EC2
- AWS Systems Manager
- AWS CLI

## Implementation
1. Created a private S3 bucket.
2. Configured S3 Block Public Access.
3. Created a custom IAM policy.
4. Attached the policy to an EC2 IAM role.
5. Connected to EC2 using Systems Manager Session Manager.
6. Uploaded a file from EC2 to S3 using AWS CLI.
7. Downloaded the file from S3 to EC2.
8. Verified IAM permissions and Linux filesystem permissions.

## IAM Security
Implemented least-privilege access using:
- s3:ListBucket
- s3:GetObject
- s3:PutObject
- s3:DeleteObject

## Testing
- Successfully uploaded an object to S3.
- Successfully downloaded the object.
- Verified downloaded file contents.
- Troubleshot IAM AccessDenied and Linux permission errors.

## Key Learnings
- S3 bucket security
- IAM policies and roles
- EC2 instance profiles
- AWS CLI operations
- Linux file permissions
- AWS troubleshooting

##Troubleshooting & Challenges
  1. IAM s3:PutObject AccessDenied.
  2. Linux /home directory permission denied during download.


## Screenshots
[Project implementation screenshots will be added here.](https://github.com/samkr321/Aws-cloud-portfolio/tree/main/02-S3-IAM-Secure-Storage/screenshots)

## Outcome
Successfully implemented and tested secure EC2-to-S3 file operations using IAM role-based access.
