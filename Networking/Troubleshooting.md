# Network Troubleshooting

## Purpose

Network troubleshooting is the process of identifying, isolating, and resolving network communication issues.

The objective is not to guess the cause of a problem.

The objective is to systematically determine where communication is failing and identify the root cause using evidence.

Successful network troubleshooting answers four questions:

```text
What is failing?
Where is it failing?
Why is it failing?
How do I verify the fix?
```

---

# Core Troubleshooting Principles

## Verify Before Assuming

Never assume a root cause.

Every conclusion should be based on evidence gathered through testing and observation.

Example:

```text
Poor Conclusion:
"The network is down."

Evidence-Based Conclusion:
"The device cannot reach its default gateway."
```

Always work from facts.

---

## Start With The Simplest Checks

Check basic causes before investigating complex ones.

Examples:

- Network cable disconnected
- Wi-Fi disabled
- Incorrect IP configuration
- Missing default gateway
- Incorrect DNS server
- VPN disconnected

Many network issues are caused by simple configuration or connectivity problems.

---

## Follow The Network Path

Think about how traffic travels through the network.

```text
Client
↓
Local Network
↓
Default Gateway
↓
Remote Network
↓
Destination Service
```

The goal is to identify where communication stops.

---

## Isolate The Problem

Reduce variables whenever possible.

Examples:

```text
Test another cable
Test another switch port
Test another device
Test another DNS server
Test another network
```

If the issue follows the device, the problem is likely device-related.

If the issue remains on the network, the problem is likely infrastructure-related.

---

# Network Troubleshooting Process

The majority of network problems can be investigated using the following workflow.

```text
Physical Connectivity
        ↓
IP Configuration
        ↓
Local Connectivity
        ↓
Gateway Connectivity
        ↓
Internet Connectivity
        ↓
DNS Resolution
        ↓
Routing Verification
        ↓
Application Connectivity
        ↓
Packet Analysis
```

---

# Step 1 – Verify Physical Connectivity

Determine whether the device has a physical or wireless connection.

Check:

- Network Cable
- Link Lights
- Access Point Connection
- Network Adapter Status
- Wi-Fi Signal Strength

Questions:

```text
Is the device connected?
Is the interface operational?
```

Common Symptoms:

```text
No Connection
Network Cable Unplugged
Disconnected Wi-Fi
```

---

# Step 2 – Verify IP Configuration

Confirm the device has valid network settings.

Verify:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Servers

Commands:

```text
ipconfig
ipconfig /all
```

Common Findings:

```text
169.254.x.x
→ DHCP Failure

Missing Gateway
→ Cannot Reach Remote Networks

Incorrect DNS Server
→ DNS Resolution Problems
```

---

# Step 3 – Verify Local Connectivity

Determine whether the device can communicate within its own network.

Tests:

```text
Ping Localhost
Ping Own IP Address
Ping Another Local Device
```

Example:

```powershell
ping 127.0.0.1
ping 192.168.1.100
```

Questions:

```text
Is the network adapter functioning?
Can the device communicate locally?
```

---

# Step 4 – Verify Gateway Connectivity

Test communication with the default gateway.

Example:

```powershell
ping 192.168.1.1
```

Questions:

```text
Can traffic leave the local device?
Can the device reach the local network boundary?
```

Common Findings:

```text
Gateway Reachable
→ Continue Testing

Gateway Unreachable
→ Local Network Problem
```

---

# Step 5 – Verify Internet Connectivity

Determine whether traffic can leave the local network.

Example:

```powershell
ping 8.8.8.8
```

Questions:

```text
Can the device reach external networks?
```

Common Findings:

```text
Success
→ Internet Reachable

Failure
→ Routing, Gateway, ISP, or Firewall Problem
```

---

# Step 6 – Verify DNS Resolution

Determine whether hostnames can be resolved.

Example:

```powershell
nslookup google.com
```

Questions:

```text
Can names be resolved into IP addresses?
```

Diagnostic Pattern:

```text
8.8.8.8 Reachable
google.com Unreachable

→ DNS Problem
```

Common Symptoms:

- Websites Fail To Load
- Server Name Not Found
- Applications Cannot Reach Hosts

---

# Step 7 – Verify Routing

Determine whether traffic is being sent to the correct destination.

Commands:

```text
route print
```

```text
tracert
```

Verify:

```text
Default Route Exists
Valid Gateway Exists
Traffic Follows Expected Path
```

Common Findings:

```text
Missing Default Route
→ Cannot Reach External Networks

Unexpected Route
→ Traffic Sent To Wrong Destination
```

---

# Step 8 – Verify Application Connectivity

Network connectivity does not guarantee service availability.

Questions:

```text
Can the host be reached?
Can the service be reached?
Is the correct port open?
```

Examples:

```powershell
Test-NetConnection server01 -Port 443
```

```powershell
curl https://example.com
```

Common Findings:

```text
Host Reachable
Port Closed

→ Service or Firewall Issue
```

---

# Step 9 – Perform Packet Analysis

If all previous testing appears normal but the issue remains, inspect network traffic directly.

Tools:

```text
Wireshark
Packet Capture Tools
```

Use Packet Analysis To Verify:

- DNS Queries
- TCP Handshakes
- Routing Behavior
- Packet Loss
- Retransmissions
- Protocol Errors

Packet captures provide direct visibility into network communication.

---

# OSI-Based Troubleshooting

The OSI model provides a structured framework for network troubleshooting.

| Layer | Question | Common Issues |
|---------|----------|----------|
| Physical | Can signals travel? | Cable, Port, Hardware |
| Data Link | Can devices communicate locally? | ARP, Duplicate IP, Switching Issues |
| Network | Can traffic reach other networks? | IP, Gateway, Routing |
| Transport | Can the service be reached? | Closed Ports, Firewall Rules |
| Application | Is the service functioning? | DNS, Web Services, Application Errors |

---

## Layer 1 – Physical

Question:

```text
Can signals travel?
```

Check:

- Cable Connections
- Switch Ports
- Fiber Connections
- Link Lights
- Wireless Signal Strength

Common Issues:

- Bad Cable
- Failed Port
- Hardware Failure
- Wireless Interference

---

## Layer 2 – Data Link

Question:

```text
Can devices communicate locally?
```

Check:

- MAC Addresses
- ARP Resolution
- Switch Connectivity

Common Issues:

- ARP Problems
- Duplicate IP Addresses
- Switching Issues

---

## Layer 3 – Network

Question:

```text
Can traffic reach another network?
```

Check:

- IP Address
- Subnet Mask
- Default Gateway
- Routing

Common Issues:

- Incorrect IP Configuration
- Missing Gateway
- Routing Problems

---

## Layer 4 – Transport

Question:

```text
Can the service be reached?
```

Check:

- TCP Connectivity
- UDP Communication
- Port Availability

Common Issues:

- Closed Ports
- Firewall Restrictions
- Connection Timeouts

---

## Layer 7 – Application

Question:

```text
Is the application functioning correctly?
```

Check:

- DNS Resolution
- Web Services
- APIs
- Authentication Services

Common Issues:

- DNS Failures
- Service Outages
- Application Errors

---

# Common Network Problems

## No Network Connectivity

Symptoms:

```text
Cannot Access Any Resource
```

Investigation Path:

```text
Physical Connection
↓
Network Adapter
↓
IP Address
↓
Gateway
```

Likely Causes:

- Cable Problem
- Adapter Failure
- DHCP Failure

---

## No Internet Access

Symptoms:

```text
Local Resources Work
Internet Resources Fail
```

Investigation Path:

```text
Gateway
↓
Public IP Reachability
↓
Routing
```

Likely Causes:

- Gateway Failure
- Routing Issue
- ISP Problem

---

## DNS Issues

Symptoms:

```text
IP Addresses Work
Hostnames Fail
```

Investigation Path:

```text
DNS Configuration
↓
DNS Queries
↓
DNS Server Availability
```

Likely Causes:

- Incorrect DNS Server
- DNS Service Failure
- Network Restrictions

---

## Cannot Reach A Specific Server

Symptoms:

```text
Only One Host Is Unreachable
```

Investigation Path:

```text
Reachability
↓
Routing
↓
Port Testing
↓
Service Status
```

Likely Causes:

- Server Offline
- Port Blocked
- Service Down

---

## Slow Network Performance

Symptoms:

```text
High Latency
Slow Applications
Packet Loss
```

Investigation Path:

```text
Latency Testing
↓
Route Analysis
↓
Packet Loss Analysis
↓
Traffic Inspection
```

Likely Causes:

- Congestion
- Packet Loss
- Poor Routing
- Bandwidth Saturation

---

## Intermittent Connectivity

Symptoms:

```text
Connection Works Sometimes
Connection Fails Sometimes
```

Investigation Path:

```text
Physical Layer
↓
Wireless Signal Quality
↓
Packet Loss
↓
Network Stability
```

Likely Causes:

- Faulty Cable
- Wireless Interference
- Unstable Network Device
- Network Congestion

---

# DHCP Troubleshooting

## Common Symptoms

```text
169.254.x.x Address
No Network Connectivity
Cannot Reach Internet
```

### Investigation Process

```text
Verify Link Status
        ↓
Verify DHCP Server Reachability
        ↓
Release / Renew Address
        ↓
Verify Lease Assignment
        ↓
Verify Gateway and DNS
```

### Common Causes

```text
DHCP Server Unavailable
DHCP Scope Exhausted
Network Cable Issue
Incorrect VLAN Assignment
DHCP Relay Failure
```

### Indicators

#### APIPA Address

```text
169.254.x.x
```

Typically indicates the device failed to obtain an IP address from DHCP.

#### Missing Gateway

```text
IP Address Present
Gateway Missing
```

Can indicate incomplete DHCP configuration.

---

# VLAN Troubleshooting

## Purpose

VLAN issues often appear as connectivity issues even when a device has a valid IP address.

A device may communicate successfully within one VLAN while being unable to reach resources in another VLAN.

---

## Common Symptoms

```text
Can Reach Some Devices
Cannot Reach Other Networks
Cannot Reach Gateway
Intermittent Connectivity
```

### Investigation Process

```text
Verify IP Configuration
        ↓
Verify Assigned VLAN
        ↓
Verify Switch Port Configuration
        ↓
Verify Gateway Availability
        ↓
Verify Inter-VLAN Routing
```

### Common Causes

```text
Wrong VLAN Assignment
Incorrect Switch Port Configuration
Missing Trunk Configuration
Inter-VLAN Routing Failure
Gateway Misconfiguration
```

### Example Scenario

```text
User Receives IP Address
        ↓
Can Reach Devices In Same VLAN
        ↓
Cannot Reach Devices In Other VLANs
```

Likely Cause:

```text
Inter-VLAN Routing Problem
```

---

# Linux Troubleshooting Commands

The following Linux commands provide functionality similar to commonly used Windows networking commands.

| Purpose | Windows | Linux |
|----------|----------|----------|
| View IP Configuration | ipconfig | ip address |
| View Routing Table | route print | ip route |
| Test Connectivity | ping | ping |
| Trace Route | tracert | traceroute |
| DNS Lookup | nslookup | nslookup |
| View Connections | netstat | ss |
| View ARP Entries | arp -a | ip neigh |
| Test Web Connectivity | curl | curl |

Examples:

### View Network Configuration

```bash
ip address
```

---

### View Routing Table

```bash
ip route
```

---

### View Active Connections

```bash
ss -tulpn
```

---

### View ARP Neighbor Table

```bash
ip neigh
```

---

### Trace Network Path

```bash
traceroute google.com
```

---

# Troubleshooting Decision Trees

## Device Cannot Access Internet

```text
No Internet
      ↓
Has IP Address?
      ↓ No
DHCP Investigation

      ↓ Yes
Can Reach Gateway?
      ↓ No
Local Network Issue

      ↓ Yes
Can Reach Public IP?
      ↓ No
Routing / ISP Issue

      ↓ Yes
Can Resolve Hostname?
      ↓ No
DNS Issue

      ↓ Yes
Application Issue
```

---

## Cannot Access Website

```text
Website Unreachable
         ↓
DNS Resolves?
         ↓ No
DNS Issue

         ↓ Yes
Can Reach Server?
         ↓ No
Routing / Connectivity Issue

         ↓ Yes
Port Reachable?
         ↓ No
Firewall / Service Issue

         ↓ Yes
Application Issue
```

---

## Slow Network

```text
Slow Network
      ↓
High Latency?
      ↓
Packet Loss?
      ↓
Congestion?
      ↓
Service Bottleneck?
```

---

# Symptom-To-Cause Reference

## APIPA Address (169.254.x.x)

Likely Cause:

```text
DHCP Failure
```

---

## Can Ping IP But Not Hostname

Likely Cause:

```text
DNS Issue
```

---

## Can Reach Gateway But Not Internet

Likely Cause:

```text
Routing Issue
ISP Issue
Firewall Restriction
```

---

## Connection Timeout

Likely Cause:

```text
Firewall Restriction
Service Unavailable
Routing Issue
```

---

## Connection Refused

Likely Cause:

```text
Target Service Not Listening
Port Closed
```

---

## Intermittent Connectivity

Likely Cause:

```text
Packet Loss
Bad Cable
Wireless Interference
Network Congestion
```

---

## High Latency

Likely Cause:

```text
Congestion
Poor Routing
Bandwidth Saturation
```

---

# Network Troubleshooting Checklist

## Physical Layer

```text
☐ Verify cable connection
☐ Verify link lights
☐ Verify wireless connectivity
☐ Verify adapter status
```

---

## IP Configuration

```text
☐ Verify IP address
☐ Verify subnet mask
☐ Verify default gateway
☐ Verify DNS servers
```

---

## Connectivity

```text
☐ Ping localhost
☐ Ping own IP
☐ Ping gateway
☐ Ping public IP
```

---

## DNS

```text
☐ Verify DNS server
☐ Run nslookup
☐ Test hostname resolution
```

---

## Routing

```text
☐ Verify default route
☐ Check traceroute
☐ Verify gateway path
```

---

## Application Access

```text
☐ Verify host reachability
☐ Verify port reachability
☐ Verify service availability
```

---

## Advanced Analysis

```text
☐ Check packet loss
☐ Review active connections
☐ Capture packets if required
```

---

# Key Takeaways

Successful network troubleshooting is based on process, not guesswork.

Remember:

- Start at the Physical Layer.
- Verify IP configuration before testing services.
- Test connectivity progressively.
- Follow the network path.
- Isolate where communication fails.
- Verify DNS before assuming Internet failure.
- Validate routing before investigating applications.
- Use packet captures when basic testing cannot identify the issue.
- Verify the root cause before implementing fixes.
- Confirm the resolution after changes are made.

The goal of network troubleshooting is not to find a quick fix.

The goal is to accurately identify where communication breaks and resolve the actual cause of the problem.
