# Active Directory Home Lab

This section documents active directory concepts and troubleshooting
exercises completed as part of my System Administration home lab.

## Week 3 - Active Directory Fundamentals

### Day 1 - Active Directory Domain Services and Domain Controller Setup

### Objective

Install Active Directory Domain Services on DC01 and create a new
Active Directory domain for the home lab.

### Environment

Server:
- DC01
- Windows Server

Domain:
- homelab.local

### Tasks Completed

- Verified DC01 network connectivity.
- Installed Active Directory Domain Services.
- Promoted DC01 to a Domain Controller.
- Created a new Active Directory forest.
- Created the `homelab.local` domain.
- Installed DNS as part of Domain Controller promotion.
- Verified domain authentication after restart.
- Opened Active Directory Users and Computers.
- Confirmed DC01 appears in the Domain Controllers container.
- Opened DNS Manager and reviewed the new domain DNS environment.

### Commands and Tools Used

```text
hostname
whoami
ipconfig /all
dsa.msc
dnsmgmt.msc
```

Server Manager

Add Roles and Features

### Key Concepts

Active Directory provides centralized management of users, computers,
groups, authentication, and access.

A Domain Controller is a Windows Server running Active Directory Domain
Services.

A Windows Server does not become a Domain Controller until AD DS is
installed and the server is promoted.

DNS is tightly integrated with Active Directory because domain clients
need DNS to locate Domain Controllers and domain services.

### What I Learned

Active Directory centralizes identity and access management for
domain-connected systems.

DC01 now acts as the first Domain Controller and DNS server for the
`homelab.local` domain.

### Day 2 - Organizational Units

### Objective

Create an Organizational Unit structure for organizing users and
computers within the homelab.local Active Directory domain.

### OU Structure

```text
homelab.local
└── Company
    ├── Employees
    │   ├── IT
    │   ├── HR
    │   ├── Sales
    │   └── Accounting
    ├── Computers
    └── Disabled Users
```

### Tasks Completed

- Opened Active Directory Users and Computers.
- Created a top-level Company OU.
- Created department OUs for IT, HR, Sales, and Accounting.
- Created separate OUs for computers and disabled accounts.
- Enabled Advanced Features in Active Directory Users and Computers.
- Practiced creating and safely deleting a test OU.

### Tools Used

`dsa.msc`

Active Directory Users and Computers

### Key Concepts

Organizational Units are containers used to organize Active Directory
objects such as users and computers.

OUs can be used to target Group Policy and delegate administrative
responsibilities.

An OU does not automatically grant access to resources. Security groups
are typically used to manage permissions.

### What I Learned

OUs provide structure inside Active Directory and make it easier to
manage users, computers, policies, and administrative responsibilities.

Organizational structure and resource permissions are separate concepts.

### Day 3 - Active Directory User Management

### Objective

Create and manage domain user accounts within the homelab.local
Active Directory environment.

### Users Created

- Alex Johnson - Sales
- Sarah Wilson - HR
- Mike Anderson - IT
- Jessica Brown - Accounting

### Tasks Completed

- Created domain user accounts.
- Placed users in the appropriate departmental OUs.
- Assigned temporary passwords.
- Required password changes at next logon.
- Reviewed user account properties.
- Added department information.
- Disabled and re-enabled a user account.
- Practiced moving an account to the Disabled Users OU.
- Reset a user's password.
- Queried Active Directory users with PowerShell.

### Commands and Tools Used

```text
dsa.msc

whoami

Get-ADUser -Filter *

Get-ADUser alex.johnson
```

### Key Concepts

Domain accounts are centrally managed through Active Directory.

A local account belongs to a specific computer, while a domain account
can be recognized by systems joined to the domain.

Disabling an account prevents login without immediately deleting the
user object.

Administrators can reset forgotten passwords and require users to create
a new password during their next logon.

### What I Learned

Active Directory allows administrators to centrally manage the full
lifecycle of user accounts, including account creation, password resets,
disabling, re-enabling, and organizational placement.

### Day 4 - Active Directory Groups

### Objective

Create security groups and use group membership to organize access
within the homelab.local domain.

### Groups Created

- GG_IT
- GG_HR
- GG_Sales
- GG_Accounting

All groups were configured as:

- Global scope
- Security type

### Tasks Completed

- Created a Groups OU.
- Created departmental security groups.
- Added users to their appropriate groups.
- Reviewed group membership through user properties.
- Practiced removing and re-adding group members.
- Queried Active Directory groups using PowerShell.

### Commands and Tools Used

```text
dsa.msc
Get-ADGroup -Filter *
Get-ADGroup GG_HR
Get-ADGroupMember GG_HR
Get-ADPrincipalGroupMembership sarah.wilson
```

### Key Concepts

Security groups are used to collect users and assign access to resources.

Organizational Units and groups serve different purposes:

- OUs organize objects and help target Group Policy.
- Groups are commonly used to manage access and permissions.

Permissions should generally be assigned to groups rather than directly
to individual users when possible.

### What I Learned

Group-based access is easier to manage than assigning permissions to
individual users.

When a user's job or department changes, updating group membership can
change their access without modifying each resource individually.
