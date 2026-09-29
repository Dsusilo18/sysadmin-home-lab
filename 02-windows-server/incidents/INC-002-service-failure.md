# INC-002 - Application Service Failure

## Reported Issue

User reported that an application hosted on DC01 was unavailable.

## Initial Checks

Verified the server identity using:

`hostname`

Reviewed network configuration using:

`ipconfig /all`

Confirmed that the server had a valid IP configuration.

## Connectivity Testing

Verified:

- local TCP/IP functionality
- default gateway connectivity
- external network connectivity
- DNS resolution

Network connectivity appeared normal.

## Service Investigation

Reviewed Windows Services using:

`services.msc`

The application service was configured for automatic startup but was found in a stopped state.

## Log Investigation

Opened Event Viewer and reviewed:

- System logs
- Application logs

A related error was found around the time of the reported outage.

The event indicated that the application service terminated unexpectedly.

## Port Review

Used:

`netstat -ano`

to review listening ports.

The application's expected port was not listening while the service was stopped.

## Root Cause

The issue was isolated to the application service rather than general network connectivity.

## Troubleshooting Conclusion

The server remained reachable and the network was functioning correctly.

The application became unavailable because its required Windows service had stopped unexpectedly.

## Skills Practiced

- Windows Server administration
- Network troubleshooting
- Service troubleshooting
- Event Viewer
- Port inspection
- Root cause isolation

## What I Learned

A reachable server does not guarantee that every application hosted on it is available.

Troubleshooting should verify network connectivity, service state, listening ports, and logs before determining the cause of an outage.