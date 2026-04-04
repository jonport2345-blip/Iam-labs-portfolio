# Azure Entra ID Lab: RBAC Implementation

## Objective
Implement role-based access control (RBAC) using Microsoft Entra ID by creating users, groups, and assigning least-privilege roles.

---

## Environment
- Microsoft Azure (Free Account)
- Microsoft Entra ID (Azure Active Directory)

---

## What I Did

### 1. User Creation
- Created multiple users:
  - John Doe
  - Jane Smith
- Assigned unique usernames and enabled accounts

### 2. Group Creation
- Created a security group:
  - **SOC-Tier1-Readonly**
- Designed to simulate a Tier 1 Security Operations team

### 3. Group Membership
- Added users to the SOC group
- Demonstrated centralized access management

### 4. Role Assignment (RBAC)
- Assigned **Directory Readers** role
- Applied role to users via group membership
- Enforced **least privilege access**

---

## Key Concepts Demonstrated
- Identity & Access Management (IAM)
- Role-Based Access Control (RBAC)
- Microsoft Entra ID
- User provisioning
- Group-based access control
- Least privilege principle

---

## Screenshots

#![User Creation](./IMG_34748552-5668-483F-8874-0CD1060C.jpeg)

#![Group Creation](./IMG_8B3D4B15-0A52-4D50-A41B-FB34950E.jpeg)

![Group Membership](./IMG_233A01A1-2B19-4910-8209-5674DD211.jpeg)

![Role Assignment](./IMG_3B69EB5A-F392-4FEA-89FD-6AD86FFC.jpeg)
---

## Outcome
Successfully implemented RBAC in Microsoft Entra ID by assigning least-privileged access to users through group-based role assignments.
