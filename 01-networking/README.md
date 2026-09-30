# Networking Fundamentals

This section documents networking concepts and troubleshooting
exercises completed as part of my System Administration home lab.

## Week 1 - Networking Fundamentals

### Day 1 - Basic Network Configuration

Topics practiced:

- IPv4 addressing
- Subnet masks
- Default gateways
- DHCP
- DNS
- Basic connectivity testing

### Commands Used

```text
hostname
whoami
ipconfig
ipconfig /all
ping
nslookup
```

### Day 2 - DNS and Name Resolution

### Topics Practiced

- DNS fundamentals
- Name resolution
- DNS server configuration
- DNS cache
- Testing specific DNS servers
- Basic DNS troubleshooting

### Commands Used

```text
ipconfig /all
nslookup
ipconfig /displaydns
ipconfig /flushdns
```

### Day 3 - Ports, Services, TCP, and UDP

### Topics Practiced

- Ports and services
- TCP vs UDP
- ICMP vs application connectivity
- Testing specific ports
- Viewing active connections

### Commands Used

```text
ping
Test-NetConnection
netstat -ano
tasklist
```

### Day 4 - Network Troubleshooting Workflow  
  
### Topics Practiced  
  
- Structured network troubleshooting  
- IP configuration validation  
- Gateway connectivity  
- External connectivity  
- DNS troubleshooting  
- Port/service troubleshooting  
  
### Troubleshooting Workflow  
  
I practiced troubleshooting from the local system outward:  
  
1. Check IP configuration with `ipconfig /all`.  
2. Test the local TCP/IP stack using `ping 127.0.0.1`.  
3. Test connectivity to the default gateway.  
4. Test external IP connectivity.  
5. Test DNS resolution using `nslookup`.  
6. Test connectivity to the destination.  
7. Test the required service port using `Test-NetConnection`.  
  
### Key Concept  
  
Different tests isolate different parts of the network.  
  
For example, if external IP connectivity works but DNS resolution fails,  
I would investigate DNS rather than assuming the entire network is down.  
  
If a server responds to ping but a specific TCP port is unreachable,  
I would investigate the service, firewall, and port configuration.  
  
### What I Learned  
  
Effective troubleshooting means testing one layer at a time and using  
the results to narrow down the location of the problem instead of  
randomly changing settings.  