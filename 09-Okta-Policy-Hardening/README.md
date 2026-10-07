# Okta Policy Hardening – Apex Finance Portal

## Project Overview

This project demonstrates the implementation and validation of hardened authentication controls for a sensitive financial application using Okta Identity Cloud.

The fictional organization, Apex Technology Group, required stronger authentication controls for its Apex Finance Portal to reduce unauthorized access risk and enforce stronger identity security.

During this lab, I configured an OpenID Connect (OIDC) application, implemented a dedicated high-security authentication policy, enforced multi-factor authentication requirements, assigned a test user, tested unauthorized access scenarios, and analyzed Okta System Log events to validate the security controls.

## Objectives

- Configure an OIDC application in Okta
- Implement a dedicated high-security authentication policy
- Enforce two-factor authentication for sensitive application access
- Control user access through application assignments
- Test authorized and unauthorized access scenarios
- Investigate authentication and authorization events using the Okta System Log
- Document security findings and validation evidence

- ## Lab Environment

- Platform: Okta Integrator Free Plan
- Application: Apex Finance Portal
- Application Protocol: OpenID Connect (OIDC)
- Authentication: Password + Okta Verify / FastPass
- Security Control: Application Sign-On Policy
- Test Identity: Ava Williams
- Monitoring: Okta System Log

## Architecture

The lab models a sensitive finance application protected by Okta.

Authentication flow:

User → Okta Identity Provider → Authentication Policy → MFA Verification → Apex Finance Portal

Access is controlled through both identity authentication and application assignment. Users must be assigned to the application and satisfy the high-security authentication policy before access is permitted.

## Implementation

### 1. Created the Apex Finance Portal

Created a new OpenID Connect (OIDC) application named **Apex Finance Portal** in Okta.

The application was configured with client credentials and OIDC redirect settings to establish the authentication flow.

### 2. Created a High-Security Authentication Policy

Created a dedicated application sign-on policy named:

**Apex- High Security Applications**

The policy was designed specifically for sensitive Apex applications requiring stronger authentication controls.

### 3. Enforced Multi-Factor Authentication

Created the **Apex- High Security MFA** rule and configured it to require two factor types.

Authentication requirements included:

- Password or Okta Verify FastPass
- An additional authentication factor
- Re-authentication every 1 hour

The Apex Finance Portal was then associated with the high-security authentication policy.

### 4. Created a Test Identity

Created a test user named **Ava Williams** to validate application access and authentication behavior.

The user was activated in Okta and used to test both authorized and unauthorized access scenarios.

### 5. Configured Application Assignment

Initially, the test user did not have access to the Apex Finance Portal.

The application was then explicitly assigned to Ava Williams, demonstrating application-level access control and the principle that successful authentication alone does not automatically authorize access to a protected application.

## Security Testing & Findings

### Test 1 – Unauthorized Application Access

**Scenario:**  
The test user, Ava Williams, attempted to access the protected environment before having the required application authorization.

**Expected Result:**  
Access should be denied.

**Actual Result:**  
Okta denied the request and returned a **403 Access Forbidden** response.

**Result:** PASS

This demonstrated that authentication alone does not guarantee authorization to a protected resource.

### Test 2 – Application Assignment

Ava Williams was explicitly assigned to the **Apex Finance Portal**.

The assignment established the user's authorization relationship with the OIDC application and allowed the identity to be evaluated against the application's authentication controls.

**Result:** PASS

### Test 3 – High-Security Authentication Policy

The Apex Finance Portal was associated with the **Apex- High Security Applications** policy.

The **Apex- High Security MFA** rule required two factor types and periodic re-authentication.

**Result:** PASS

### Test 4 – System Log Investigation

Okta System Log events were reviewed to validate identity activity.

Observed events included:

- User creation and activation
- Application assignment
- Authentication attempts
- Successful authentication events
- Unauthorized application access failures
- Sign-on policy evaluation
- OIDC authorization and token activity

The logs provided audit evidence showing both successful and failed identity events.

**Result:** PASS

## Security Findings

The testing demonstrated multiple layers of identity security:

1. **Authentication and authorization are separate controls.** A valid Okta identity does not automatically receive access to every application.
2. **Application assignments restrict access.** Users must have an authorized relationship with the protected application.
3. **Strong authentication protects sensitive resources.** The finance application was placed behind a dedicated MFA policy.
4. **System Logs provide auditability.** Authentication, authorization, application assignment, and policy events can be investigated through Okta's logging capabilities.
5. **Denied access is valuable security evidence.** The 403 response confirmed that an unauthorized access attempt was blocked as designed.

## Remediation and Security Improvements

Based on testing, the following controls were implemented to strengthen the Apex Finance Portal:

- Restricted application access to explicitly assigned users
- Applied a dedicated high-security authentication policy
- Required two factor types for sensitive application access
- Configured periodic re-authentication
- Used Okta Verify / FastPass as an available authentication factor
- Monitored authentication and authorization activity through the Okta System Log
- Validated access controls through both successful and failed access scenarios

These controls demonstrate a defense-in-depth approach where application assignment, authentication policy, MFA, and monitoring work together to protect sensitive resources.

## Skills Demonstrated

- Okta Identity and Access Management
- OpenID Connect (OIDC)
- Multi-Factor Authentication (MFA)
- Application Sign-On Policies
- Application Assignment
- Authentication vs. Authorization
- Identity Lifecycle Administration
- Access Control Testing
- Okta System Log Analysis
- Security Policy Hardening
- Troubleshooting Authentication and Authorization
- Identity Security Monitoring

## Lessons Learned

This project reinforced that securing an application requires more than simply authenticating a user.

A properly designed IAM control combines authentication, authorization, application assignment, strong authentication policies, and continuous logging.

The unauthorized access test was especially valuable because it demonstrated how Okta blocks access when the required authorization relationship is missing. Reviewing the System Log also showed how IAM administrators can trace identity events and use audit data to investigate access issues.

The project provided hands-on experience designing, implementing, testing, and validating identity security controls rather than only configuring individual Okta features.

## Evidence and Screenshots

The following screenshots document the configuration, access-control testing, MFA enforcement, and System Log validation performed during this project.

### 1. High-Security MFA Policy

Shows the enabled **Apex- High Security MFA** rule requiring two factor types and stronger authentication controls.

![High-Security MFA Policy](screenshots/857ABE50-5C27-44C6-A966-9644F859F106.png)

### 2. Test User – Apex Finance Portal Assignment

Shows the Ava Williams test identity assigned to the **Apex Finance Portal** for access-control validation.

![Apex Finance Portal Assignment](screenshots/D3393CF6-6C6B-4358-ADD6-16DB32CE5B7C.png)

### 3. Unauthorized Access – 403 Forbidden

Demonstrates negative authorization testing. An unauthorized access attempt resulted in a **403 Access Forbidden** response.

![403 Access Forbidden](screenshots/9C942316-BFA3-4999-A498-32C7145CB463.png)

### 4. Unauthorized Access – System Log Evidence

Shows Okta System Log events recording failed unauthorized access attempts, providing audit evidence that the access restriction operated as expected.

![Unauthorized Access System Log](screenshots/7A5F7015-4595-4BC2-84A0-D48ED10D7C49.png)

### 5. Authentication and OIDC System Log Evidence

Shows successful OIDC authorization and token activity captured in the Okta System Log during validation.

![OIDC System Log Evidence](screenshots/41C0C49E-EA0E-40F9-BC5C-8A8BBC33FE82.jpeg)

### 6. MFA and Authentication Validation

Shows successful user authentication, MFA activity, sign-on policy evaluation, and OIDC token events used to validate the hardened authentication controls.

![MFA Authentication Validation](screenshots/377A1801-FD94-45D4-928C-94DF5F5920F0.png)
## Project Outcome

Successfully implemented and validated a hardened authentication model for a sensitive OIDC application using Okta.

The project demonstrated application-level authorization, multi-factor authentication enforcement, policy-based access control, negative access testing, troubleshooting, and audit-log analysis.

The final configuration showed that identity security controls were functioning as intended and that unauthorized access attempts could be identified and investigated through Okta.
