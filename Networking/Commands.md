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

Key information:

- IPv4 Address
- IPv6 Address
- Subnet Mask
- Default Gateway
- DNS Servers

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

Questions answered:

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

Questions answered:

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

Questions answered:

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

Questions answered:

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

Questions answered:

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

Questions answered:

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

# Interface Testing

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

# Network Configuration Testing

## Test-NetConnection (PowerShell)

Tests network connectivity and port access.

Example:

```powershell
Test-NetConnection google.com -Port 443
```

Questions answered:

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

Useful for:

- API Testing
- Web Server Testing
- Connectivity Verification

Questions answered:

```text
Can I reach the service?
Is the application responding?
```

---

# Packet Analysis

## Wireshark

Packet capture and protocol analysis tool.

Purpose:

```text
Inspect Network Traffic
```

Useful for:

- Deep Troubleshooting
- Protocol Analysis
- Packet Inspection

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
