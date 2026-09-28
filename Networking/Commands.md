# Networking Commands

## Purpose

Networking commands are tools used to inspect, test, and troubleshoot network communication.

They help administrators answer questions such as:

- Does the device have an IP address?
- Can the device reach the network?
- Can the device reach the Internet?
- Is DNS working?
- What path is traffic taking?
- Which connections are active?
- How is routing configured?

Understanding what a command tells you is more important than memorizing syntax.

---

# Troubleshooting Workflow

A simple workflow for most networking issues:

```text
1. Verify IP Configuration
        ↓
2. Verify Local Connectivity
        ↓
3. Verify Gateway Connectivity
        ↓
4. Verify Internet Connectivity
        ↓
5. Verify DNS Resolution
        ↓
6. Verify Routing and Active Connections
```

The commands in this document support each stage of that process.

---

# IP Configuration

## ipconfig (Windows)

Displays IP configuration information.

Common uses:

```text
View IP Address
View Gateway
View DNS Servers
```

Examples:

```powershell
ipconfig
```

```powershell
ipconfig /all
```

Sample Output:

```text
Ethernet adapter Ethernet:

   IPv4 Address. . . . . . . . . . : 192.168.1.100
   Subnet Mask . . . . . . . . . . : 255.255.255.0
   Default Gateway . . . . . . . . : 192.168.1.1
```

Key Information:

```text
IPv4 Address     = Device Address
Subnet Mask      = Network Boundary
Default Gateway  = Path to Other Networks
```

Use when:

```text
First step in most troubleshooting scenarios.
```

---

## ifconfig (Legacy Linux/macOS)

Displays network interface information.

Example:

```bash
ifconfig
```

Commonly replaced by:

```bash
ip address
```

---

## ip (Linux)

Modern Linux networking utility.

Examples:

```bash
ip address
```

```bash
ip route
```

Used to:

- View Interfaces
- View Addresses
- View Routes

---

# Connectivity Testing

## ping

Tests reachability between devices using ICMP.

Example:

```bash
ping 8.8.8.8
```

Sample Output:

```text
Reply from 8.8.8.8:
bytes=32 time=15ms TTL=117

Reply from 8.8.8.8:
bytes=32 time=14ms TTL=117

Ping statistics:
    Packets: Sent = 2, Received = 2, Lost = 0 (0% loss)
```

Key Information:

```text
time = Latency
TTL  = Remaining Hop Count
Loss = Packet Loss Percentage
```

Healthy Result:

```text
0% packet loss
Consistent response times
```

Questions Answered:

```text
Can I reach the destination?
```

Common uses:

- Verify Local Connectivity
- Verify Gateway Access
- Verify Internet Connectivity
- Verify Host Reachability

---

## tracert (Windows)

Displays the path traffic takes to reach a destination.

Example:

```powershell
tracert google.com
```

Sample Output:

```text
Tracing route to google.com

  1    <1 ms     <1 ms     <1 ms  192.168.1.1
  2     5 ms      5 ms      4 ms  isp-router
  3     9 ms      8 ms      9 ms  upstream-router
  4    15 ms     14 ms     15 ms  google.com
```

Key Information:

```text
Each line = Network Hop

Increasing latency is normal.

Timeouts may indicate:
- Filtering
- Congestion
- Routing Issues
```

Questions Answered:

```text
Where is communication failing?
```

---

## traceroute (Linux/macOS)

Linux and macOS equivalent of tracert.

Example:

```bash
traceroute google.com
```

Use when:

- Diagnosing path issues
- Identifying problematic hops
- Investigating latency

---

# DNS Troubleshooting

## nslookup

Queries DNS servers.

Example:

```bash
nslookup google.com
```

Sample Output:

```text
Server:  dns.company.local
Address: 10.0.0.10

Non-authoritative answer:
Name:    google.com
Address: 142.250.190.46
```

Key Information:

```text
Server  = DNS Server Used
Name    = Requested Hostname
Address = Resolved IP Address
```

Healthy Result:

```text
Hostname successfully resolves.
```

Questions Answered:

```text
Can DNS resolve names?
```

Useful for:

- DNS Issues
- Name Resolution Problems
- DNS Server Verification

---

## Resolve-DnsName (PowerShell)

Provides detailed DNS query results.

Example:

```powershell
Resolve-DnsName google.com
```

Useful for:

- Advanced DNS Troubleshooting
- DNS Record Verification

---

# Network Connections

## netstat

Displays active connections and listening ports.

Example:

```powershell
netstat -ano
```

Sample Output:

```text
Proto  Local Address         Foreign Address       State
TCP    192.168.1.100:50432   142.250.190.46:443   ESTABLISHED
TCP    192.168.1.100:49611   10.0.0.10:53         ESTABLISHED
```

Key Information:

```text
Local Address   = Your Device
Foreign Address = Remote Device
State           = Connection State
```

Common States:

```text
LISTENING
ESTABLISHED
TIME_WAIT
CLOSE_WAIT
```

Questions Answered:

```text
What connections are active?
What ports are listening?
```

Useful for:

- Connectivity Issues
- Service Verification
- Security Investigations

---

## ss (Linux)

Modern replacement for netstat.

Example:

```bash
ss -tulpn
```

Useful for:

- Viewing Active Connections
- Viewing Listening Services

---

# ARP Inspection

## arp

Displays and manages ARP entries.

Example:

```powershell
arp -a
```

Sample Output:

```text
Interface: 192.168.1.100

Internet Address      Physical Address      Type
192.168.1.1           aa-bb-cc-dd-ee-ff     dynamic
192.168.1.10          11-22-33-44-55-66     dynamic
```

Key Information:

```text
Internet Address = IP Address
Physical Address = MAC Address
Type             = Dynamic or Static
```

Questions Answered:

```text
Which MAC addresses have been learned?
```

Useful for:

- Local Network Troubleshooting
- Duplicate IP Investigations
- Address Resolution Problems

---

# Routing

## route

Displays or modifies routing information.

Example:

```powershell
route print
```

Sample Output:

```text
IPv4 Route Table

Network Destination    Netmask          Gateway
0.0.0.0                0.0.0.0          192.168.1.1
192.168.1.0            255.255.255.0    On-link
```

Key Information:

```text
0.0.0.0/0 = Default Route

Gateway = Next-Hop Device
```

Healthy Result:

```text
A valid default route exists.
```

Questions Answered:

```text
How is traffic being routed?
```

Useful for:

- Gateway Problems
- Routing Issues
- Network Reachability Problems

---

## ip route (Linux)

Displays routing information.

Example:

```bash
ip route
```

Useful for:

- Route Verification
- Gateway Verification

---

# Network Performance Testing

## pathping (Windows)

Combines ping and traceroute functionality.

Example:

```powershell
pathping google.com
```

Useful for:

- Packet Loss Analysis
- Network Performance Troubleshooting

---

# Port Connectivity Testing

## Test-NetConnection (PowerShell)

Tests network connectivity and port access.

Example:

```powershell
Test-NetConnection google.com -Port 443
```

Sample Output:

```text
ComputerName     : google.com
RemoteAddress    : 142.250.190.46
RemotePort       : 443
TcpTestSucceeded : True
```

Key Information:

```text
TcpTestSucceeded = Port Reachability
```

Healthy Result:

```text
TcpTestSucceeded : True
```

Questions Answered:

```text
Can I reach the host?
Can I reach the service port?
```

Useful for:

- Firewall Validation
- Service Availability Testing
- Port Connectivity Checks

---

# Web Connectivity

## curl

Transfers data to and from servers.

Example:

```bash
curl https://example.com
```

Sample Output:

```text
HTTP/1.1 200 OK

<html>
  ...
</html>
```

Key Information:

```text
200 = Success
301 = Redirect
403 = Forbidden
404 = Not Found
500 = Server Error
```

Questions Answered:

```text
Can I reach the service?
Is the application responding?
```

Useful for:

- Web Server Testing
- API Testing
- Connectivity Verification
- Application Troubleshooting

---

# Packet Analysis

## Wireshark

Packet capture and protocol analysis tool.

Purpose:

```text
Inspect Network Traffic
```

Example Packet View:

```text
No.  Time      Source          Destination     Protocol
1    0.000     192.168.1.100   8.8.8.8         DNS
2    0.020     8.8.8.8         192.168.1.100   DNS
3    0.030     192.168.1.100   142.250.x.x     TCP
4    0.045     142.250.x.x     192.168.1.100   TCP
```

Key Information:

```text
Source      = Sender
Destination = Receiver
Protocol    = Traffic Type
Time        = Packet Timing
```

Useful for:

- Deep Troubleshooting
- Protocol Analysis
- Packet Inspection
- Root Cause Analysis

Wireshark allows administrators to view network traffic at the packet level.

---

# Essential Commands Summary

The commands most frequently used during troubleshooting are:

```text
ipconfig
ping
tracert
nslookup
arp
netstat
route
Test-NetConnection
curl
Wireshark
```

Mastering these commands will solve the majority of day-to-day networking problems encountered in IT Operations and Support.

---

# Command Selection Guide

```text
Need to verify IP settings?
→ ipconfig

Need to test connectivity?
→ ping

Need to find where connectivity is failing?
→ tracert / traceroute

Need to test DNS?
→ nslookup

Need to inspect ARP entries?
→ arp

Need to view active connections?
→ netstat

Need to inspect routing?
→ route

Need to test a specific port?
→ Test-NetConnection

Need to test a web service?
→ curl

Need deep packet analysis?
→ Wireshark
```

---

# Key Takeaways

When troubleshooting networking issues, focus on answering these questions in order:

```text
1. Do I have an IP address?
2. Can I reach my gateway?
3. Can I reach the destination?
4. Can DNS resolve names?
5. Is the route correct?
6. Is the service reachable?
7. What do the packets show?
```

The most important commands for day-to-day IT Operations are:

- ipconfig
- ping
- tracert / traceroute
- nslookup
- arp
- netstat
- route
- Test-NetConnection
- curl
- Wireshark

Knowing when to use a command is more valuable than memorizing every available option.
