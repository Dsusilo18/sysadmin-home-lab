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

homelab.local
└── Company
    ├── Employees
    │   ├── IT
    │   ├── HR
    │   ├── Sales
    │   └── Accounting
    ├── Computers
    └── Disabled Users

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