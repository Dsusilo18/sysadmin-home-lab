# Windows Client and Domain Join

### Day 1 - CLIENT01 Setup and Network Preparation

### Objective

Create a Windows client virtual machine and prepare it for communication
with the homelab.local Active Directory environment.

### Lab Environment

Server:
- DC01
- Windows Server
- Active Directory Domain Services
- DNS

Client:
- CLIENT01
- Windows client operating system

### CLIENT01 VM Configuration

- 4 GB RAM
- 2 virtual CPUs
- 50 GB dynamically allocated storage

### Tasks Completed

- Created the CLIENT01 virtual machine.
- Installed Windows.
- Created a local administrative account.
- Renamed the workstation to CLIENT01.
- Reviewed IPv4 and DNS configuration.
- Tested network connectivity between CLIENT01 and DC01.
- Reviewed the internal DNS environment hosted by DC01.
- Tested name resolution for the Domain Controller.

### Commands and Tools Used

```text
hostname
ipconfig /all
ping
nslookup
Get-DnsClientServerAddress
dnsmgmt.msc
```

### Key Concepts

A Windows client uses services provided by Windows Server.

Before a client can successfully join an Active Directory domain, it
must have network connectivity to the Domain Controller and be able to
resolve the domain using the appropriate DNS server.

Public DNS servers do not contain records for private Active Directory
domains such as homelab.local.

### What I Learned

Domain connectivity depends on both basic IP networking and DNS.

A client may be able to reach a Domain Controller by IP address while
still being unable to locate the Active Directory domain if its DNS
configuration is incorrect.
