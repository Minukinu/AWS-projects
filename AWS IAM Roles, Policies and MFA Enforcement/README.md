# AWS IAM Roles, Policies and MFA Enforcement

## Project Overview

This project demonstrates the implementation of secure access control in AWS using IAM (Identity and Access Management). It includes creating IAM users, assigning policies, configuring roles, and enforcing Multi-Factor Authentication (MFA) to enhance account security.

##  Objectives

* Create IAM users with limited permissions
* Implement custom and managed IAM policies
* Configure IAM roles for AWS services
* Enable Multi-Factor Authentication (MFA)
* Enforce MFA-based access control
* Test security by allowing and denying access

##  Services Used

* AWS IAM (Identity and Access Management)
* Amazon EC2
* Amazon S3

## ⚙️ Implementation Steps

### 1. Create IAM User

* Created a user named **developer-user**
* Enabled AWS Management Console access
* Assigned initial read-only permissions

### 2. Attach Policies

* Attached AWS managed policies:

  * AmazonEC2ReadOnlyAccess
  * AmazonS3ReadOnlyAccess
* Created and attached a custom policy for controlled access

### 3. Create Custom Policy

* Allowed:

  * EC2 Describe actions
  * S3 bucket listing
* Used JSON-based policy configuration

### 4. Create IAM Role

* Created role: **EC2-ReadOnly-Role**
* Trusted entity: EC2
* Attached custom policy

### 5. Attach Role to EC2

* Linked IAM role to EC2 instance
* Enabled secure access without storing credentials

### 6. Enable MFA

* Configured MFA for IAM user
* Used authenticator app (Google/Microsoft Authenticator)

### 7. Enforce MFA Policy

* Created MFA enforcement policy
* Denied access if MFA is not enabled
* Allowed access only when MFA is verified

### 8. Testing

* Without MFA → Access Denied 
* With MFA → Access Granted 

##  Security Features Implemented

* Least Privilege Access
* Role-Based Access Control (RBAC)
* MFA Enforcement
* Secure access to AWS services

##  Screenshots
## Screenshots

### IAM User Creation
![IAM User](screenshots/iam-user.png)

### Policy Creation
![Policy](screenshots/policy.png)

### Role Creation
![Role](screenshots/role.png)

### EC2 Role Attachment
![EC2 Role](screenshots/ec2-role.png)

### MFA Setup
![MFA](screenshots/mfa.png)

### Access Denied Test
![Access Denied](screenshots/access-denied.png)

### Access Allowed Test
![Access Allowed](screenshots/access-allowed.png)

##Architecture Diagram

graph TD

User[Admin/User] --> IAM[AWS IAM]

IAM --> IAMUser[IAM User]
IAM --> Policy[Custom Policy]
IAM --> Role[IAM Role]
IAM --> MFA[MFA
## Outcome

Successfully implemented a secure AWS environment using IAM roles, policies, and MFA enforcement to prevent unauthorized access and ensure strong authentication.

##  Key Learnings
* Understanding of IAM components (Users, Roles, Policies)
* Hands-on experience with AWS security best practices
* Importance of MFA in cloud environments
* Implementation of real-world access control

##  Conclusion
This project highlights how AWS IAM can be used to manage access securely. MFA enforcement adds an extra layer of protection, making the system more robust against unauthorized access.

## Author
MenikaJha
