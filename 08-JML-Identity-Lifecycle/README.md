# 🔐 Joiner-Mover-Leaver (JML) Identity Lifecycle Management

## Project Overview

This project demonstrates a hands-on **Joiner-Mover-Leaver (JML) identity lifecycle workflow** using Microsoft Entra ID.

The objective was to simulate how an IAM team manages a user's identity and access throughout the employee lifecycle—from initial onboarding, through a job-role change, to termination and access removal.

The lab focuses on identity provisioning, role-based group access, access modification, and secure deprovisioning.

---

## 🛠 Technologies Used

- Microsoft Entra ID
- Microsoft Azure
- Security Groups
- Role-Based Access Control (RBAC)
- Identity Lifecycle Management
- Joiner-Mover-Leaver (JML) Processes

---

## 🏢 Business Scenario

A fictional organization, **Apex Technologies**, hires a new employee named **Marcus Johnson**.

Marcus begins as a **Help Desk Analyst** and requires access appropriate for Tier 1 IT support.

Later, Marcus transfers into a **SOC Analyst** position. His previous Help Desk access must be removed and replaced with access appropriate for his new responsibilities.

Finally, Marcus leaves the organization. His account must be disabled and his access removed to prevent unauthorized access.

This demonstrates three critical IAM lifecycle events:

**JOINER → MOVER → LEAVER**

---

# 🟢 Phase 1 — JOINER

Marcus Johnson joins Apex Technologies as a **Help Desk Analyst**.

### Identity Provisioning

A new Microsoft Entra ID identity was created with:

- **User:** Marcus Johnson
- **Job Title:** Help Desk Analyst
- **Company:** Apex Technologies
- **Department:** Information Technology
- **User Type:** Member
- **Account Status:** Enabled

### Access Provisioning

A security group was created:

`HelpDesk-Tier1`

Marcus was added to the group to simulate role-based access provisioning.

### IAM Principle

Instead of assigning access individually, access is managed through **security-group membership**.

This supports:

- Role-based access
- Consistent provisioning
- Easier access reviews
- Scalable identity administration
- Least-privilege access management

---

# 🟡 Phase 2 — MOVER

Marcus transfers from **Help Desk Analyst** to **SOC Analyst**.

His identity attributes were updated to reflect the new job function.

### Access Change

His previous Help Desk access was removed:

`HelpDesk-Tier1`

He was then assigned to:

`SOC-Tier1-Readonly`

This demonstrates how IAM teams modify access when an employee changes roles.

### IAM Principle

A role change should trigger an access review.

Old access should be removed before or alongside the provisioning of new access to reduce **access accumulation** and unnecessary privileges.

---

# 🔴 Phase 3 — LEAVER

Marcus leaves Apex Technologies.

The offboarding process included:

1. Disabling the Microsoft Entra ID account
2. Removing the user from the SOC security group
3. Verifying that no group memberships remained
4. Confirming the account remained disabled

### Final State

- **Account Status:** Disabled
- **Group Memberships:** 0
- **Applications:** 0
- **Assigned Roles:** 0
- **Assigned Licenses:** 0

This ensures the identity can no longer be used to access organizational resources through the provisioned account.

---

## 🔄 Identity Lifecycle Flow

`JOINER → Help Desk Analyst → HelpDesk-Tier1`

⬇️

`MOVER → SOC Analyst → SOC-Tier1-Readonly`

⬇️

`LEAVER → Account Disabled → Group Access Removed`

---

## 🔐 Security Concepts Demonstrated

- Joiner-Mover-Leaver (JML)
- Identity Lifecycle Management
- User Provisioning
- User Deprovisioning
- Role-Based Access Control (RBAC)
- Security Group Management
- Least Privilege
- Access Revocation
- Identity Attribute Management
- Prevention of Access Accumulation

---

## 💡 Key Takeaways

This project demonstrated that identity management extends beyond simply creating and deleting user accounts.

Effective IAM requires managing access throughout the complete identity lifecycle.

The **Mover** phase is particularly important because users can accumulate unnecessary privileges when changing roles if previous access is not properly reviewed and revoked.

The **Leaver** process demonstrates the importance of promptly disabling identities and removing access when users leave an organization.

---

## 📸 Lab Evidence

Screenshots documenting each stage of the lifecycle will be added here:

### Joiner
- User identity creation
- Help Desk job attributes
- HelpDesk-Tier1 group membership

### Mover
- Job title changed to SOC Analyst
- HelpDesk-Tier1 access removed
- SOC-Tier1-Readonly access assigned

### Leaver
- Account disabled
- SOC group membership removed
- Final state showing zero group memberships

---

## 🎯 Skills Demonstrated

**Microsoft Entra ID | Identity Lifecycle Management | JML | RBAC | User Provisioning | Deprovisioning | Security Groups | Access Management | Least Privilege**
