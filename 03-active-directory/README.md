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