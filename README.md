# AWS IAM Practical – Users, Groups, and Policies

## Overview
This practical demonstrates core AWS Identity and Access Management (IAM) concepts by creating users, groups, and assigning policies. The goal was to understand how AWS evaluates permissions using user policies, group policies, and deny rules.

---

## Objectives
- Create IAM users and groups
- Assign AWS managed policies
- Observe how permissions are inherited via groups
- Understand implicit deny, explicit deny, and policy evaluation

---

## Tools & Environment
- AWS Management Console
- AWS Free Tier Account
- AWS IAM Service

---

## Practical Steps

### 1. Create IAM Group
- Created a group named `developers-group`
- Attached policy: `AmazonEC2FullAccess` & `AmAmazonS3FullAccess `
- Purpose: Manage permissions centrally for multiple users

---

### 2. Create IAM User
- Created IAM user: `test-user-001`
- Enabled AWS Management Console access
- No policies attached directly at creation

---

### 3. Add User to Group
- Added `test-user-001` to the `developers-group` group
- User inherited S3 full access and EC2 full access from the group

---

### 4. Attach User Policy (Testing Scenario)
- Attached `AWSLambdaFullAccess` directly to the user
- Purpose: Test how user and group policies combine

---

## Observations & Key Learnings
- IAM permissions are **additive** across user and group policies
- Group policies **do not overwrite** user policies
- **Explicit Deny** always overrides Allow
- Any action not explicitly allowed is **implicitly denied**
- Groups are the recommended way to manage permissions at scale

---

## Security Best Practices
- Follow the principle of least privilege
- Use IAM groups instead of individual user policies
- Avoid using the root account for daily tasks
- Enable MFA for IAM users in production environments

---

## Conclusion
This practical reinforced AWS IAM fundamentals and demonstrated how permissions are evaluated in AWS using user policies, group policies, and deny rules.

---

## Next Steps
- Test role-based access instead of long-term credentials
- Explore IAM policy JSON structure in depth
