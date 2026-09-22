# Windows Server Fundamentals

This section documents windows server concepts and troubleshooting
exercises completed as part of my System Administration home lab.

## Week 2 - Windows Server Fundamentals

### Day 1 - Windows Server Installation and Introduction  
  
### Objective  
  
Create a Windows Server virtual machine and become familiar with the  
basic Windows Server environment and Server Manager.  
  
### Lab Environment  
  
Host:  
- Windows 10  
  
Virtualization:  
- VirtualBox  
  
Windows Server VM:  
- 4 GB RAM  
- 2 virtual CPUs  
- 50 GB dynamically allocated storage  
- Windows Server Desktop Experience  
  
### Tasks Completed  
  
- Created a Windows Server virtual machine.  
- Installed Windows Server.  
- Logged in using the local Administrator account.  
- Explored Server Manager.  
- Reviewed Local Server information.  
- Identified the server hostname and network configuration.  
- Reviewed running Windows services.  
- Viewed active and listening network connections.  
  
### Commands Used  

```text
hostname  
whoami
ipconfig  
winver 
Get-Service  
netstat -ano
```  
  
### Key Concepts  
  
Windows Server is designed to provide centralized services and resources  
to other systems and users.  
  
Server roles define major jobs that a Windows Server performs, such as  
DNS, DHCP, file services, and Active Directory Domain Services.  
  
A virtual machine behaves like an independent computer even though it  
shares physical resources with the host computer.  
  
### What I Learned  
  
Installing Windows Server alone does not automatically make the machine  
a Domain Controller or DNS server. Server roles must be installed and  
configured based on the purpose of the server.  