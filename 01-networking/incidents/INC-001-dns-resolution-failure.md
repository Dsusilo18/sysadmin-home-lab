# INC-001 - DNS Resolution Failure  
  
## Reported Issue  
  
User reported that websites could not be reached and believed the internet connection was down.  
  
## Troubleshooting Process  
  
### 1. Verified Network Configuration  
  
Command:  
  
`ipconfig /all`  
  
Verified that the system had:  
  
- IPv4 address  
- subnet mask  
- default gateway  
- configured DNS server  
  
### 2. Tested Local TCP/IP  
  
Command:  
  
`ping 127.0.0.1`  
  
Result:  
  
Successful.  
  
This indicated that the local TCP/IP stack was functioning.  
  
### 3. Tested Local Gateway  
  
Command:  
  
`ping <default-gateway>`  
  
Result:  
  
Successful.  
  
This indicated that the computer could communicate with the local network gateway.  
  
### 4. Tested External IP Connectivity  
  
Command:  
  
`ping 8.8.8.8`  
  
Result:  
  
Successful.  
  
This indicated that external IP connectivity was available.  
  
### 5. Tested DNS Resolution  
  
Command:  
  
`nslookup google.com`  
  
Result:  
  
Failed.  
  
### 6. Tested Another DNS Server  
  
Command:  
  
`nslookup google.com 8.8.8.8`  
  
Result:  
  
Successful.  
  
## Root Cause  
  
The configured DNS server was not successfully resolving the hostname.  
  
## Troubleshooting Conclusion  
  
The issue was not a complete internet outage.  
  
The computer had working:  
  
- local networking  
- gateway connectivity  
- external IP connectivity  
  
The failure occurred during DNS name resolution.  
  
## Skills Practiced  
  
- Network troubleshooting  
- IP configuration validation  
- Gateway testing  
- External connectivity testing  
- DNS troubleshooting  
- `ipconfig`  
- `ping`  
- `nslookup`  
  
## What I Learned  
  
A user may report that the internet is unavailable even when general network connectivity is working.  
  
Testing the network in stages helps isolate whether the problem is local connectivity, routing, DNS, or a specific service.  