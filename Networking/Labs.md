# Networking Labs

## Purpose

The purpose of these labs is to reinforce networking concepts through practical exercises.

These labs focus on:

- Understanding how networking works
- Observing protocols in action
- Practicing troubleshooting methods
- Building operational experience

The goal is not simply to complete tasks.

The goal is to understand why networking behaves the way it does.

---

# Fundamentals Labs

## Lab 1 – Identify Network Components

### Objective

Identify the networking components used by your device.

### Tasks

- Identify your network adapter
- Determine whether you are using Ethernet or Wi-Fi
- Identify your IPv4 address
- Identify your MAC address
- Identify your default gateway

### Expected Outcome

Understand the basic components required for network communication.

---

## Lab 2 – Trace A Communication Path

### Objective

Visualize how data travels through a network.

### Tasks

Map the path between:

```text
Your Device
↓
Default Gateway
↓
ISP
↓
Internet
↓
Destination Website
```

### Expected Outcome

Understand how devices communicate across multiple networks.

---

## Lab 3 – OSI Layer Mapping

### Objective

Relate networking components to the OSI model.

### Tasks

Identify which OSI layer is responsible for:

- Ethernet Cable
- MAC Address
- IP Address
- TCP
- DNS
- Web Browser

### Expected Outcome

Understand how the OSI model organizes networking functions.

---

# Protocol Labs

## Lab 4 – DNS Resolution

### Objective

Observe DNS name resolution.

### Tasks

Run:

```bash
nslookup google.com
```

Answer:

- Which DNS server responded?
- Which IP address was returned?
- What happens if DNS fails?

### Expected Outcome

Understand how DNS converts names into IP addresses.

---

## Lab 5 – DHCP Investigation

### Objective

Observe DHCP-assigned settings.

### Tasks

Record:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Servers

Questions:

- Which values were likely assigned by DHCP?
- What would happen if DHCP became unavailable?

### Expected Outcome

Understand DHCP's role in network configuration.

---

## Lab 6 – ARP Table Exploration

### Objective

Observe local address resolution.

### Tasks

Run:

```bash
arp -a
```

or

```bash
ip neigh
```

Identify:

- IP addresses
- MAC addresses
- Gateway entry

### Expected Outcome

Understand how local devices discover MAC addresses.

---

## Lab 7 – TCP vs UDP Research

### Objective

Compare transport protocols.

### Tasks

Identify applications that use:

```text
TCP
```

and

```text
UDP
```

Explain:

- Why reliability matters
- Why speed matters

### Expected Outcome

Understand the tradeoff between reliability and performance.

---

# Commands Labs

## Lab 8 – Verify Network Configuration

### Objective

Inspect device configuration.

### Tasks

Run:

```bash
ipconfig /all
```

or

```bash
ip address
```

Record:

- IP Address
- Subnet Mask
- Gateway
- DNS Servers

### Expected Outcome

Become familiar with network configuration information.

---

## Lab 9 – Connectivity Testing

### Objective

Test connectivity at different points.

### Tasks

Ping:

```text
127.0.0.1
```

```text
Your IP Address
```

```text
Your Gateway
```

```text
8.8.8.8
```

Compare the results.

### Expected Outcome

Understand progressive connectivity testing.

---

## Lab 10 – Route Discovery

### Objective

Observe how traffic travels across networks.

### Tasks

Run:

```bash
tracert google.com
```

or

```bash
traceroute google.com
```

Identify:

- Number of hops
- First hop
- Final destination

### Expected Outcome

Understand network path traversal.

---

## Lab 11 – Active Connections

### Objective

Inspect current network connections.

### Tasks

Run:

```bash
netstat -ano
```

or

```bash
ss -tulpn
```

Identify:

- Active Connections
- Listening Ports

### Expected Outcome

Understand how devices maintain network sessions.

---

## Lab 12 – Port Testing

### Objective

Verify service availability.

### Tasks

Run:

```powershell
Test-NetConnection google.com -Port 443
```

or

```bash
curl https://google.com
```

Determine:

- Is the service reachable?
- Is the port open?

### Expected Outcome

Understand application-level connectivity testing.

---

# Troubleshooting Labs

## Lab 13 – DNS Failure Simulation

### Objective

Identify and troubleshoot a DNS issue.

### Scenario

A user can ping:

```text
8.8.8.8
```

but cannot access:

```text
google.com
```

### Tasks

Determine:

- What works?
- What fails?
- What is the likely cause?

### Expected Outcome

Identify a DNS-related problem.

---

## Lab 14 – No Internet Scenario

### Objective

Follow a troubleshooting process.

### Scenario

A user reports:

```text
No Internet Access
```

### Tasks

Perform:

```text
IP Check
↓
Gateway Check
↓
Internet Check
↓
DNS Check
```

Document findings.

### Expected Outcome

Practice systematic network troubleshooting.

---

## Lab 15 – Gateway Failure Scenario

### Objective

Recognize gateway-related issues.

### Scenario

Device has:

```text
Valid IP Address
```

but cannot ping:

```text
Default Gateway
```

### Tasks

Identify possible causes.

### Expected Outcome

Understand the role of the default gateway.

---

## Lab 16 – Service Unreachable

### Objective

Distinguish network issues from service issues.

### Scenario

A server responds to:

```text
Ping
```

but users cannot access:

```text
HTTPS
```

### Tasks

Investigate:

- Port Availability
- Service Status
- Firewall Rules

### Expected Outcome

Understand the difference between host connectivity and service availability.

---

## Lab 17 – VLAN Troubleshooting

### Objective

Investigate a VLAN issue.

### Scenario

User can communicate with devices in the same VLAN but cannot reach devices in another VLAN.

### Tasks

Investigate:

```text
Gateway
↓
VLAN Assignment
↓
Inter-VLAN Routing
```

### Expected Outcome

Understand common VLAN-related issues.

---

## Lab 18 – DHCP Failure Scenario

### Objective

Identify DHCP issues.

### Scenario

Device receives:

```text
169.254.x.x
```

### Tasks

Determine:

- What the address indicates
- Potential causes
- Troubleshooting steps

### Expected Outcome

Understand APIPA and DHCP failures.

---

## Lab 19 – High Latency Investigation

### Objective

Analyze slow network performance.

### Scenario

Users report:

```text
Slow Internet
```

### Tasks

Use:

```text
ping
tracert
pathping
```

Document observations.

### Expected Outcome

Understand latency and packet loss analysis.

---

## Lab 20 – Packet Analysis Introduction

### Objective

Observe network traffic.

### Tasks

Capture traffic using Wireshark.

Identify:

- DNS Request
- DNS Response
- TCP Handshake
- HTTPS Traffic

### Expected Outcome

Understand how protocols appear in network traffic.

---

# Capstone Lab

## Lab 21 – Complete Network Investigation

### Objective

Apply Fundamentals, Protocols, Commands, and Troubleshooting together.

### Scenario

A user reports:

```text
I cannot access a website.
```

### Investigation Process

```text
Physical Connectivity
↓
IP Configuration
↓
Gateway Testing
↓
Internet Testing
↓
DNS Testing
↓
Route Verification
↓
Port Verification
↓
Packet Analysis
```

### Deliverables

Document:

- Symptoms
- Tests Performed
- Findings
- Root Cause
- Resolution

### Expected Outcome

Perform a complete networking investigation using a structured troubleshooting methodology.

---
