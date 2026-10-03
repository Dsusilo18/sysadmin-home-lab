# INC-003 - New Employee Onboarding

## Request

Create an Active Directory account for a new HR employee, Emily Davis.

## Tasks Completed

- Created the `emily.davis` domain account.
- Placed the account in the HR Organizational Unit.
- Assigned a temporary password.
- Required the user to change the password at next logon.
- Added the user to the `GG_HR` security group.
- Added HR department information to the user object.
- Verified the account was enabled.
- Verified group membership.

## Account Structure

User:
Emily Davis

Username:
emily.davis

OU:
Company/Employees/HR

Security Group:
GG_HR

## Verification

Used Active Directory Users and Computers and PowerShell to verify the
user object and group membership.

### Commands Used

`Get-ADUser emily.davis`

`Get-ADPrincipalGroupMembership emily.davis`

## Troubleshooting Exercise

Removed the user from the HR security group to simulate an access issue,
then verified that missing group membership could prevent access to HR
resources.

The user was then added back to the correct group.

## Key Concepts

Organizational Units determine where Active Directory objects are
organized and where policies may apply.

Security groups are commonly used to grant access to resources.

A user can be located in the correct OU while still lacking required
permissions if they are missing the correct security group membership.

## What I Learned

New user onboarding involves more than creating an account.

The administrator must verify correct OU placement, account status,
password configuration, and security group membership before the user is
ready to access organizational resources.