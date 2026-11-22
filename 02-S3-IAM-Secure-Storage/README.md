# AWS S3 Secure Storage with IAM Role-Based Access

## Project Overview

Implemented a secure AWS S3 storage solution using IAM role-based access from an Amazon EC2 instance. The project demonstrates secure file operations between EC2 and S3 without storing AWS access keys on the EC2 instance.

## AWS Services Used

- Amazon S3
- AWS IAM
- Amazon EC2
- AWS Systems Manager (Session Manager)
- AWS CLI

## Implementation

1. Created a private S3 bucket.
2. Configured S3 Block Public Access.
3. Created a custom IAM policy with required S3 permissions.
4. Attached the policy to an EC2 IAM role.
5. Connected to EC2 using Systems Manager Session Manager.
6. Uploaded a file from EC2 to S3 using AWS CLI.
7. Downloaded the file from S3 to EC2.
8. Verified IAM permissions and Linux filesystem permissions.

## IAM Security

Implemented role-based access using an EC2 IAM role and a custom least-privilege policy.

Permissions used for the file operations:

- `s3:ListBucket`
- `s3:GetObject`
- `s3:PutObject`

No long-term AWS access keys were stored on the EC2 instance.

## Testing and Verification

- Successfully uploaded an object to S3.
- Successfully downloaded the object from S3.
- Verified downloaded file contents.
- Troubleshot IAM AccessDenied and Linux filesystem permission errors.

## Troubleshooting & Challenges

1. Resolved IAM `s3:PutObject` AccessDenied errors by correcting the IAM policy.
2. Resolved Linux `/home` directory permission issues during file download.

## Key Learnings

- S3 bucket security and Block Public Access.
- IAM policies, roles, and instance profiles.
- Secure EC2-to-S3 communication.
- AWS CLI operations.
- Linux filesystem permissions.
- AWS troubleshooting and access control.

## Screenshots

### 1. S3 Bucket Creation
![S3 Bucket Creation](./screenshots/01-s3-bucket-creation.JPG)

### 2. S3 Encryption
![S3 Encryption](./screenshots/02-s3-Encryption.JPG)

### 3. S3 Bucket Security
![S3 Bucket Security](./screenshots/03-s3-bucket-security.JPG)

### 4. IAM Policy Creation
![IAM Policy Creation](./screenshots/04-iam-policy-creation.JPG)

### 5. IAM Policy Attachment
![IAM Policy Attachment](./screenshots/05-iam-policy-attachment.JPG)

### 6. IAM Policy Verification
![IAM Policy Verification](./screenshots/06-iam-policy-attachment-verification.JPG)

### 7. EC2 SSM Connection
![EC2 SSM Connection](./screenshots/07-ec2-ssm-connection.JPG)

### 8. S3 File Upload
![S3 File Upload](./screenshots/08-s3-file-upload.JPG)

### 9. S3 File Download
![S3 File Download](./screenshots/09-s3-file-download.JPG)

### 10. File Verification
![File Verification](./screenshots/10-file-verification.JPG)

## AWS Architecture Diagram

```mermaid
flowchart TD
    A[Administrator] --> B[AWS Systems Manager Session Manager]
    B --> C[Amazon EC2 Linux Instance]
    C --> D[EC2 IAM Role]
    D --> E[Custom IAM Permissions Policy]
    C -->|AWS CLI| F[Private Amazon S3 Bucket]
    E -->|Authorizes Access| F
    F --> G[Upload File]
    F --> H[Download File]
    H --> I[Verify Downloaded File]
```

## Project Outcome

Successfully implemented and tested secure EC2-to-S3 file operations using IAM role-based access, AWS CLI, and Systems Manager Session Manager.
