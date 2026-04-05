
# AWS IAM Lab: Users, Groups, and Permissions

## Objective
Create IAM users, organize them into groups, and assign permissions using least privilege.

---

## Environment
- AWS Free Tier
- IAM (Identity and Access Management)

---

## What I Did

### 1. Created IAM Users
- Created multiple IAM users:
  - john.doe
  - jane.doe
- Verified user creation in IAM dashboard

---

### 2. Created IAM Group
- Created group:
  - S3-ReadOnly-Group
- Designed group for centralized permission management

---

### 3. Assigned Permissions
- Attached AWS managed policy:
  - AmazonS3ReadOnlyAccess
- Ensured users only have read-only access (least privilege)

---

### 4. Added Users to Group
- Added users to S3-ReadOnly-Group
- Verified group membership

---

## Key Concepts Demonstrated
- Identity & Access Management (IAM)
- Principle of Least Privilege
- Group-Based Access Control
- AWS IAM Policies
- Centralized Permission Management

---

### Screenshots

### IAM Dashboard
![IAM Dashboard](./IMG_1014.jpeg)

### Users Created
![Users Created](./IMG_1015.jpeg)

### Group Created
![Group Created](./IMG_1016.jpeg)

### Group Membership
![Group Membership](./IMG_1017.jpeg)

---

## Outcome
Successfully implemented IAM user and group management in AWS by assigning least-privileged access through group-based permissions.
